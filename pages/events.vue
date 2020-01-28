<template>
  <div>
    <nav-bar-component />
    <div class="container">
      <br><br><h1>Events</h1><hr><br>
      <ul>
        <li>2:00pm Ceremony in Chapel</li>
        <li>2:00-4:00pm Social Hour</li>
        <li>4:00pm Open Buffet</li>
        <li>5:00pm Cake Cutting</li>
        <li>7:00pm Fin</li>
      </ul>
    </div>
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
  font-family: 'Rouge Script', cursive;
  color:#000000;
  letter-spacing: 1.5px;
  font-weight: 400;
  width: 50%;
  margin-left: auto;
  margin-right:auto;
  max-width: 480px;
}

h1 {
  text-align: center;
  font-size: 250%;
}

ul, li {
  text-align: left;
  font-size: 125%;
  list-style: none;
}
</style>
