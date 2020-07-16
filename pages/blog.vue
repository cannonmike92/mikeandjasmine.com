<template>
<div>
  <nav-bar-component />
  <div v-if="loading" class="text-center">
    <b-spinner type="grow" style="width: 5rem; height: 5rem; margin-top: 10%;"></b-spinner>
  </div>
  <div v-else class="container">
    <b-card v-for="item in items" :key="item.id" style="max-width: 40rem;
        display: block;
        margin-left: auto;
        margin-right: auto;" class="mb-2">
      <p style="float:right;color:grey;">
        {{ hrDate(item.updated) }}
      </p><br><br>
      <p>{{ item.title}}</p>
      {{ item.content }}
      <p><a v-if="item.url" :href="item.url">Link</a></p>
    </b-card>
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
      items: []
    }
  },
  methods: {
    fetchData() {
      axios.get(`https://www.googleapis.com/blogger/v3/blogs/5341567129262295790/posts?key=AIzaSyCz_3EKKRn6GDXnuS1K3Islo_5nGZWm8Qc`)
        .then((response) => {
          this.items = response.data.items;
          this.loading = false;
        }).catch((err) => {
          console.log(err);
        })
    },
    hrDate(input) {
      return new Date(input).toLocaleString('en-US');
    }
  }
}
</script>

<style>
.container {
  position: relative;
  width: 90%;
  margin-left: auto;
  margin-right: auto;
  max-width: 960px;
  margin: 0 auto;
  padding: 0 20px;
  box-sizing: border-box;
}

p, h4 {
  font-family: 'Libre Baskerville';
}

.btn-outline-success {
  display: block;
  max-width: 300px;
  margin-left: auto;
  margin-right: auto;
}
</style>
<style scoped>
.grecaptcha-badge {
  display: none !important;
}
</style>
