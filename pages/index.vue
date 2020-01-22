<template>
  <div>
    <nav-bar-component />
    <h1 class="title">
      The Wedding of Jasmine Khaleel & Mike Cannon
    </h1>
    <h2 class="subheader">April 11th, 2020</h2><br>
    <div class="container">
      <b-img fluid center rounded="circle" src="~/assets/engagement-photos/RailDistrictFriscoTexasEngagement-Jasmine+Mike-KyrstenAshlayPhotography-24-Edit.jpg" alt="Engagement Ring"/>
    </div>
  </div>
</template>

<script>
import NavBar from '@/components/navbar';
import { BImg } from 'bootstrap-vue';

export default {
  components: {
    'nav-bar-component': NavBar,
    'b-img': BImg
  },
  data() {
    return {

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

.title {
  font-family: 'Rouge Script', cursive;
  text-align: center;
  font-weight: 400;
  font-size: 250%;
  color: #000000;
  letter-spacing: 1.5px;
}

.subheader {
  font-family: 'Rouge Script', cursive;
  text-align: center;
  font-weight: 400;
  font-size: 150%;
  color: #000000;
  letter-spacing: 1.5px;
}



</style>
