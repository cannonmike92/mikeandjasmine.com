<template>
<div>
  <nav-bar-component />
  <p class="subheader">Photos taken by <a href="https://kyrstenashlayphotography.com/">Kyrsten Ashlay Photography</a></p>
  <div class="container">
      <b-img-lazy v-for="(image, index) in images" :key="index" class="item" style="width:30%;" :src="require(`../assets/engagement-photos/${image}.jpg`)" />
  </div>
</div>
</template>

<script>
import NavBar from '@/components/navbar';
import {
  BImgLazy
} from 'bootstrap-vue';

export default {
  data: function() {
    return {
      images: [
        'RailDistrictFriscoTexasEngagement-Jasmine+Mike-KyrstenAshlayPhotography-15-Edit',
        'RailDistrictFriscoTexasEngagement-Jasmine+Mike-KyrstenAshlayPhotography-24-Edit',
        'RailDistrictFriscoTexasEngagement-Jasmine+Mike-KyrstenAshlayPhotography-50-Edit',
        'RailDistrictFriscoTexasEngagement-Jasmine+Mike-KyrstenAshlayPhotography-30-Edit',
        'RailDistrictFriscoTexasEngagement-Jasmine+Mike-KyrstenAshlayPhotography-36-Edit',
        'RailDistrictFriscoTexasEngagement-Jasmine+Mike-KyrstenAshlayPhotography-54-Edit',
        'RailDistrictFriscoTexasEngagement-Jasmine+Mike-KyrstenAshlayPhotography-58-Edit',
        'RailDistrictFriscoTexasEngagement-Jasmine+Mike-KyrstenAshlayPhotography-78-Edit'
      ],
      index: null
    };
  },
  components: {
    'b-img-lazy': BImgLazy,
    'nav-bar-component': NavBar
  }
}
</script>

<style scoped>
.subheader {
  font-family: 'Rouge Script', cursive;
  text-align: center;
  font-weight: 400;
  font-size: 1.5em;
  color: #000000;
  letter-spacing: 1.5px;
}
a {
  color: #000000;
}
.item {
  margin: 5px;
}
</style>
