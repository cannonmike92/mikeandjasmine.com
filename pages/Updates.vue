<template>
<div>
  <nav-bar-component />
  <div v-if="loading" class="text-center">
    <b-spinner type="grow" style="width: 5rem; height: 5rem; margin-top: 10%;"></b-spinner>
  </div>
  <div v-else>
    <h4 class="title">Recent Updates</h4>
    <b-card v-for="event in events" v-if="event.active" :key="event.guid" :title="event.title" style="max-width: 40rem;
        display: block;
        margin-left: auto;
        margin-right: auto;" class="mb-2">
      <p style="float:right;color:grey;">
        {{ hrDate(event.modified) }}
      </p>
      <p>
        {{ event.body }}
        <a v-if="event.url" :href="event.url">Link</a>
      </p>
    </b-card>
    <br>
    <b-button pill variant="outline-success" href="https://www.pushbullet.com/channel?tag=mikeandjasmine">
      Subscribe For More Updates!
      <img style="height:30px;" src="~/assets/pushbullet.png" alt="Pushbullet">
    </b-button>
  </div>
</div>
</template>

<script>
const axios = require('axios');
const moment = require('moment');
import NavBar from '@/components/navbar';
import {
  BSpinner,
  BButton,
  BCard
} from 'bootstrap-vue';
export default {
  components: {
    'nav-bar-component': NavBar,
    'b-spinner': BSpinner,
    'b-button': BButton,
    'b-card': BCard,
  },
  created() {
    this.fetchData();
  },
  data() {
    return {
      loading: true,
      events: []
    }
  },
  methods: {
    fetchData() {
      axios.get('https://api.pushbullet.com/v2/channel-info?tag=mikeandjasmine')
        .then((response) => {
          this.events = response.data.recent_pushes;
          this.loading = false;
        }).catch((err) => {
          console.log(err);
        })
    },
    hrDate(input) {
      return moment(input * 1000).format('MMM D, h:mm a');
    }
  }
}
</script>

<style>
.container {
  position: relative;
  width: 100%;
  max-width: 960px;
  margin: 0 auto;
  padding: 0 20px;
  box-sizing: border-box;
}

.btn-outline-success {
  display: block;
  max-width: 300px;
  margin-left: auto;
  margin-right: auto;
}

.title {
  font-family: 'Rouge Script', cursive;
  text-align: center;
  font-weight: 400;
  font-size: 4em;
  color: #000000;
  letter-spacing: 1.5px;
}

.subheader {
  font-family: Serif;
  text-align: center;
  font-weight: 400;
  font-size: 1.25em;
  color: #000000;
  letter-spacing: 1.5px;
}
</style>
