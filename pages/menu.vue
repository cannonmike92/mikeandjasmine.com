<template>
  <div>
    <nav-bar-component />
    <div style="max-width:768px;width:90%;margin-left:auto;margin-right:auto;">
      <br><br><h1>Menu</h1><br><br>
      <h3>Hors D'Oeuvres</h3><hr>
      <h5>Mushroom Empanadas</h5>
      <h5>Pear Crostini</h5>
      <h3>Entrees</h3><hr>
      <h5>Slow Roasted Halal Beef Brisket with Sesame Hoisin Au jus</h5>
      <h5>Chicken Fried Rice with Shiitake Mushrooms and Baby Bok Choy</h5>
      <h3>Sides</h3><hr>
      <h5>Ginger Garlic Vegetables</h5>
      <h5>Sauteed Corn</h5>
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

h1,h3 {
  text-align: center;
  font-family: 'Libre Baskerville';
  color: #000000;
}
h5 {
  font-family: 'Dancing Script';
  color: #000000;
  margin-bottom: 20px;
}
</style>
