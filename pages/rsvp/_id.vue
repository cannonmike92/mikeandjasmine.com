<template>
<div>
  <nav-bar-component />
  <div class="form-container mx-auto">
    <b-form class="mx-auto">
      <b-form-group>
        <b-form-input :disabled="id.length>0" v-model="email" type="email" required placeholder="Contact Email" />
        <b-form-input :disabled="id.length>0" v-model="phone" required placeholder="Contact Phone Number" />
        <b-input-group v-for="(person, index) in people" :key="index">
          <b-form-input v-model="person.firstName" required placeholder="First Name" />
          <b-form-input v-model="person.lastName" required placeholder="Last Name" />
        </b-input-group>
        <b-input-group prepend="Number in Party">
          <b-form-select @change="updateCount" v-model="count" :options="options">
          </b-form-select>
        </b-input-group>
      </b-form-group>
      <recaptcha />
      <b-button v-if="id.length" :disabled="disableSubmit" @click="update" variant="primary">
        <b-spinner v-if="loading" small/>
        Update RSVP
      </b-button>
      <b-button v-else :disabled="disableSubmit" @click="submit" variant="primary">
        <b-spinner v-if="loading" small/>
        Submit RSVP
      </b-button>
    </b-form>
  </div>
</div>
</template>
<script>
import _ from 'lodash';
import NavBar from '@/components/navbar';
import {
  BButton,
  BForm,
  BFormGroup,
  BFormInput,
  BInputGroup,
  BInputGroupPrepend
} from 'bootstrap-vue';
const axios = require('axios');

export default {
  components: {
    'nav-bar-component': NavBar,
    'b-form-group': BFormGroup,
    'b-form-input': BFormInput,
    'b-input-group': BInputGroup,
    'b-input-group-prepend': BInputGroupPrepend,
    'b-button': BButton,
    'b-form': BForm,
  },
  computed: {
    disableSubmit: function(){
      var emptyPeople = _.findIndex(this.people, function(o){
        return o.firstName == '' || o.lastName == '';
      })
      if ( this.email && this.phone && emptyPeople == -1) {
        return false;
      } else {
        return true;
      }
    }
  },
  async mounted() {
    await this.$recaptcha.init()
    if (this.$nuxt._route.params.id) {
      var self = this;
      self.id = this.$nuxt._route.params.id
      axios.get(`https://ed053gh1zc.execute-api.us-east-1.amazonaws.com/dev/${self.id}`)
        .then((response) => {
          self.email = response.data.Item.email;
          self.phone = response.data.Item.phone;
          self.people = response.data.Item.people;
          self.count = response.data.Item.people.length;
        })
    }
  },
  methods: {
    async submit() {
      var self = this
      this.loading = true;
      try {
        const token = await this.$recaptcha.execute('login')

        axios.post('https://ed053gh1zc.execute-api.us-east-1.amazonaws.com/dev', {
            rsvp: {
              'email': this.email,
              'phone': this.phone,
              'people': this.people
            },
            'token': token
          })
          .then((response) => {
            self.$bvModal.msgBoxOk('RSVP Submitted!')
              .then(value => {
                self.$router.push('/');
              })
              .catch(err => {
                // An error occurred
                console.log(err);
              })
          }).catch((err) => {
            console.log(err);
            if (err.response.status == 400) {
              console.log('Duplicate Record!')
              self.$bvModal.msgBoxOk('Duplicate RSVP! Please go to your email to find your unique RSVP link!')
                .then(value => {
                  self.$router.push('/');
                })
            }
          })
        await this.$recaptcha.reset()
      } catch (error) {
        console.log('Login error:', error)
      }
    },
    async update() {
      this.loading = true;
      var self = this
      try {
        const token = await this.$recaptcha.execute('login')

        axios.put(`https://ed053gh1zc.execute-api.us-east-1.amazonaws.com/dev/${this.id}/`, {
            rsvp: {
              'people': this.people
            },
            'token': token
          })
          .then((response) => {
            self.$bvModal.msgBoxOk('RSVP Updated!')
              .then(value => {
                // redirect to home
                self.$router.push('/');
              })
              .catch(err => {
                // An error occurred
                console.log(err);
              })
          }).catch((err) => {
            console.log(err);
          })
        await this.$recaptcha.reset()
      } catch (error) {
        console.log('Login error:', error)
      }
    },
    updateCount() {
      if (this.count > this.people.length) {
        for (var i = this.people.length; i < this.count; i++) {
          this.people.push({
            firstName: '',
            lastName: ''
          });
        }
      } else if ((this.count < this.people.length)) {
        this.people = this.people.slice(0, this.count);
      }
    }
  },
  data() {
    return {
      id: '',
      email: '',
      phone: '',
      count: 1,
      people: [{
        firstName: '',
        lastName: ''
      }],
      options: [1, 2, 3, 4, 5, 6, 7, 8],
      loading: false
    }
  }
}
</script>
<style>
form {
  max-width: 90%;
  text-align: center;
}

.form-container {
  max-width: 500px;
  margin: 20px;
}

input,
select {
  max-width: 95%;
  margin-top: 20px;
}

.input-group {
  max-width: 95%;
}

.input-group-text {
  background: none;
  border: none;
  padding-bottom: 0;
}

.g-recaptcha {
  display: inline-block;
}
</style>
