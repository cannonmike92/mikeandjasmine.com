<template>
  <div>
    <nav-bar-component />
    <br>
    <h2 class="title">
      The Windsor
    </h2>
    <h2 class="subheader">At Hebron Park</h2><br>
    <b-img style="width:60%;" src="https://www.windsorparkdallas.com/wp-content/uploads/2015/09/82.jpg"/><br>
    <h5><a href="https://goo.gl/maps/KXWdoizLWgw1PBNCA">3016 E. Hebron Parkway • Carrollton, TX 75010 </a></h5>
    <h5><a href="https://www.windsorparkdallas.com/">https://www.windsorparkdallas.com/</a></h5>
    <h5>(972)-306-3300</h5>

  </div>
</template>

<script>
import NavBar from '@/components/navbar'
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

<style scoped>
.container {
  position: relative;
  width: 100%;
  max-width: 960px;
  margin: 0 auto;
  padding: 0 10px;
  box-sizing: border-box;
}

.title {
  font-family: 'Libre Baskerville', Helvetica;
  text-align: center;
  font-size: 250%;
  color: #000000;
}

h5 {
  text-align: center;
  font-family: 'Libre Baskerville', Helvetica;
  color: #000000;
}

img {
  display:block;
  margin:auto;
  max-width:85%;
}

.subheader {
  font-family: 'Dancing Script', Helvetica;
  text-align: center;
  font-size: 150%;
  color: #000000;
}
</style>
