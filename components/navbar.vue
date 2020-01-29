<template>
  <div>
    <b-navbar toggleable="lg" type="light" variant="light" align="center">
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item>
            <nuxt-link to="/">Save the Date
              <font-awesome-icon style="font-size:75%;" icon="home"/>
            </nuxt-link>
          </b-nav-item>
          <b-nav-item>
            <nuxt-link to="/menu">Menu
            </nuxt-link></b-nav-item>
          <!--<b-nav-item>
            <nuxt-link to="/Registry">Registry
            </nuxt-link></b-nav-item>
          <b-nav-item>
            <nuxt-link to="/events">Events
            </nuxt-link></b-nav-item>
          <b-nav-item>-->
            <nuxt-link to="/location">Location
            </nuxt-link></b-nav-item>
          <b-nav-item>
            <nuxt-link to="/photos">Photos
            </nuxt-link></b-nav-item>
          <b-nav-item>
            <nuxt-link to="/rsvp">RSVP
            </nuxt-link></b-nav-item>
          <b-nav-item>
            <nuxt-link to="/updates">Updates
            </nuxt-link></b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>
<script>
import { BNav, BNavbar, BNavbarNav, BNavbarToggle, BCollapse } from 'bootstrap-vue';
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';

export default {
  name: 'NavBar',
  components: {
    'b-nav-item': BNav,
    'b-navbar': BNavbar,
    'b-navbar-nav': BNavbarNav,
    'b-navbar-toggle': BNavbarToggle,
    'b-collapse': BCollapse,
    'font-awesome-icon': FontAwesomeIcon
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
  font-size: 150%;
  color: #000000;
  font-family: 'Rouge Script', cursive;
}
</style>
<style>
.bg-light {
  background-color: #FFFFFF !important;
}
</style>
