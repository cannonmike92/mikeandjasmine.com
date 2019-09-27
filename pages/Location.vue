<template>
  <div>
    <nav-bar-component />
    <h1 class="title">
      The Windsor
    </h1>
    <h2 class="subheader">At Hebron Park</h2><br>
    <img src="https://www.windsorparkdallas.com/wp-content/uploads/2015/09/82.jpg"/>
    <h5><a href="https://goo.gl/maps/KXWdoizLWgw1PBNCA">3016 E. Hebron Parkway • Carrollton, TX 75010 </a></h5>
    <h5><a href="https://www.windsorparkdallas.com/">https://www.windsorparkdallas.com/</a></h5>
    <h5>(972)-306-3300</h5>

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

<style scoped>
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

h5 {
  text-align: center;
}

img {
  display:block;
  margin:auto;
  max-width:85%;
}

.subheader {
  font-family: 'Rouge Script', cursive;
  text-align: center;
  font-weight: 400;
  font-size: 3em;
  color: #000000;
  letter-spacing: 1.5px;
}
</style>
