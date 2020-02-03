<template>
  <div>
    <nav-bar-component />
    <div class="container">
      <br><br><h1>Events</h1><hr><br>
      <ul>
        <li>2:00pm Ceremony in Chapel</li>
        <li>2:30-3:30pm Social Hour with Refreshments and Entertainment</li>
        <li>4:00pm Dinner Begins</li>
        <li>5:00pm Cake Cutting</li>
        <li>7:00pm Farewell</li>
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
  font-family: 'Dancing Script', Helvetica;
  color:#000000;
  width: 90%;
  margin-left: auto;
  margin-right:auto;
  max-width: 480px;
}

h1 {
  font-family: 'Libre Baskerville', Helvetica;
  text-align: center;
  font-size: 250%;
}

ul, li {
  text-align: left;
  font-size: 125%;
  list-style: none;
}

li {
  margin: 20px;
}
</style>
