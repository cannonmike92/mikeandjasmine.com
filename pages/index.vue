<template>
  <div>
    <nav-bar-component />
    <!--<p>Click <nuxt-link to="/RSVP">here</nuxt-link> to RSVP!</p>-->
    <div style="margin-top: 20px;">
      <h1 class="title">
        The Wedding of Jasmine Khaleel & Mike Cannon
      </h1>
      <h2 class="subheader">April 11th, 2020</h2><br>
      <div class="container">
        <b-img
          fluid center rounded="circle"
          src="~/assets/engagement-photos/RailDistrictFriscoTexasEngagement-Jasmine+Mike-KyrstenAshlayPhotography-24-Edit.jpg"
          alt="Engagement Ring"/>
      </div>
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
  font-family: 'Dancing Script';
  text-align: center;
  color: #000000;
}

.subheader {
  font-family: 'Libre Baskerville';
  text-align: center;
  font-size: 100%;
  color: #000000;
}

p {
  font-family: 'Dancing Script';
  font-weight: 400;
  text-align: center;
}
</style>
<style scoped>
@media only screen and (min-width: 992px) {
  p {
    display: none;
  }
}


</style>
