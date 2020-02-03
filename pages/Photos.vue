<template>
<div>
  <nav-bar-component />
  <p class="subheader">Photos taken by <a href="https://kyrstenashlayphotography.com/">Kyrsten Ashlay Photography</a></p>
  <div class="container">
    <div
      :key="index"
      class="item"
      v-for="(image, index) in images"
      @click="openModal(image)">
      <b-img-lazy
        fluid
        :src="require(`../assets/engagement-photos/${image}.jpg`)" />
    </div>
  </div>
  <b-modal v-model="showModal" hide-footer hide-header size="xl">
   <b-img-lazy
      fluid
     :src="require(`../assets/engagement-photos/${modalImage}.jpg`)" />
 </b-modal>
</div>
</template>

<script>
import NavBar from '@/components/navbar';
import {
  BModal,
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
      index: null,
      showModal: false,
      modalImage: 'RailDistrictFriscoTexasEngagement-Jasmine+Mike-KyrstenAshlayPhotography-15-Edit'
    };
  },
  methods: {
    openModal(image) {
      console.log(image);
      this.modalImage = image;
      this.showModal = true;
    },
    closeModal() {
      this.showModal = false;
    }
  },
  components: {
    'b-modal': BModal,
    'b-img-lazy': BImgLazy,
    'nav-bar-component': NavBar
  }
}
</script>

<style scoped>
.subheader {
  font-family: 'Dancing Script', Helvetica;
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
  width: 32%;
}
.container {
  justify-content: center;
  display: flex;
  flex-wrap: wrap;
}
</style>
