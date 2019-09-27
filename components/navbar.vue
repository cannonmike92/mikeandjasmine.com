<template>
  <div>
    <b-navbar toggleable="lg" type="light" variant="light" align="center">
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item>
            <a href="/">Save the Date
            </a></b-nav-item>
          <!--<b-nav-item>
            <a href="/RSVP">RSVP
            </a></b-nav-item>
          <b-nav-item>
            <a href="/Registry">Registry
            </a></b-nav-item>
          <b-nav-item>
            <a href="/Schedule">Schedule
            </a></b-nav-item>-->
          <b-nav-item>
            <a href="/Location">Location
            </a></b-nav-item>
          <b-nav-item>
            <a href="/Updates">Updates
            </a></b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>
<script>
import { BNav, BNavbar, BNavbarNav, BNavbarToggle, BCollapse } from 'bootstrap-vue'

export default {
  name: 'NavBar',
  components: {
    'b-nav-item': BNav,
    'b-navbar': BNavbar,
    'b-navbar-nav': BNavbarNav,
    'b-navbar-toggle': BNavbarToggle,
    'b-collapse': BCollapse,
  },
  data() {
    return {

    }
  }
}
</script>
<style scoped>
.navbar-nav ul a{
  margin: 5px;
  margin-left: 30px;
  margin-right: 30px;
  font-weight: 400;
  font-size: 2em;
  color: #000000;
  font-family: 'Rouge Script', cursive;
}
</style>
