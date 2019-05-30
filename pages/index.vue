<template>
  <div>
  <img src="~/assets/engagement_ring.jpg" alt="Engagement Ring">
  <div><br>
    <h1 class="title">
      The Wedding of Mike Cannon & Jasmine Khaleel
    </h1>
  </div>
  </div>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'

export default {
  components: {
    AppLogo
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
  font-size: 5em;
  color: #ffffff;
  letter-spacing: 1.5px;
}

img {
  position: absolute;
  left: 0px;
  top: 0px;
  width: 100%;
  z-index: -1;
}

</style>
