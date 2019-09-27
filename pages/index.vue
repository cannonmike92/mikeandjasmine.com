<template>
  <div>
    <nav-bar-component />
    <h1 class="title">
      The Wedding of Jasmine Khaleel & Mike Cannon
    </h1>
    <h2 class="subheader">April 11th, 2020</h2><br>
    <img class="img-circle" src="~/assets/engagement_ring.jpg" alt="Engagement Ring">
  </div>
</template>

<script>
import NavBar from '@/components/navbar'
export default {
  components: {
    'nav-bar-component': NavBar
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
  font-size: 4em;
  color: #000000;
  letter-spacing: 1.5px;
}

.subheader {
  font-family: 'Rouge Script', cursive;
  text-align: center;
  font-weight: 400;
  font-size: 3em;
  color: #000000;
  letter-spacing: 1.5px;
}

.img-circle {
  border-radius: 50%;
  max-width: 85%;
  display:block;
  margin:auto;
}
</style>
