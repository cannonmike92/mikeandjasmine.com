<template>
  <div>
    <nav-bar-component />
    <b-form class="mx-auto">
      <b-form-group>
        <b-form-input
          v-model="email"
          type="email"
          required
          placeholder="Contact Email"
        />
        <b-form-input
          v-model="phone"
          required
          placeholder="Contact Phone Number"
        />
        <b-input-group v-for="(person, index) in people">
          <b-form-input
            v-model="person.firstName"
            required
            placeholder="First Name"
          />
          <b-form-input
            v-model="person.lastName"
            required
            placeholder="Last Name"
          />
        </b-input-group>
        <b-input-group prepend="Number in Party">
          <b-form-select
            @change="updateCount"
            v-model="count"
            :options="options"
          >
          </b-form-select>
        </b-input-group>
      </b-form-group>
      <recaptcha
        @error="onError"
        @success="onSuccess"
        @expired="onExpired"
      /><br>
      <b-button @click="submit" variant="primary">Submit</b-button>
    </b-form>
  </div>
</template>
<script>
import NavBar from '@/components/navbar';
import {BButton, BForm, BFormGroup, BFormInput, BInputGroup, BInputGroupPrepend} from 'bootstrap-vue';
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
  methods: {
    onSuccess (token) {
      console.log('Succeeded:', token)
    },
    onExpired () {
      console.log('Expired')
    },
    onError (error) {
      console.log('Error happened:', error)
    },
    async submit() {
      var self = this
      try {
        const token = await this.$recaptcha.getResponse()
        console.log('ReCaptcha token:', token)
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
             // do something
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
      if ( this.count > this.people.length ) {
        for(var i = this.people.length; i < this.count; i++) {
          this.people.push({
            firstName: '',
            lastName: ''
          });
        }
      } else if (( this.count < this.people.length )) {
        this.people = this.people.slice(0, this.count);
      }
    }
  },
  data() {
    return {
      email: '',
      phone: '',
      count: 1,
      people: [
        {
          firstName: '',
          lastName: ''
        }
      ],
      options: [1,2,3,4,5,6,7,8]
    }
  }
}
</script>
<style>
form {
  max-width: 90%;
  text-align: center;
}
input, select {
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
