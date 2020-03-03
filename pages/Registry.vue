<template>
<div>
    <nav-bar-component/>
    <br>
    <h2 class="title">Registry</h2>
    <br>
    <h5>Gifts are appreciated, but not essential. Your presence on our big day is a gift unto itself.</h5>
    <h5>That being said, we are registered at the following locations:</h5>
    <br>
    <b-container>
        <b-row>
          <b-col>
              <a href="https://www.target.com/gift-registry/giftgiver?registryId=f7c8b0e649cd4dd68a983da8f79e279b&type=WEDDING">
                  <b-img-lazy fluid :src="require('../assets/target_logo.png')"/>
              </a>
          </b-col>
          <b-col>
              <a href="https://www.amazon.com/wedding/mike-cannon-jasmine-khaleel--april-2020/registry/36U7Q9X4VKI7Y">
                  <b-img-lazy fluid :src="require('../assets/amazoncom-logo.png')"/>
              </a>
          </b-col>
          <b-col>
              <a href="https://www.macys.com/wgl/registry/guest/7115322">
                  <b-img-lazy fluid :src="require('../assets/macys_logo.png')"/>
              </a>
          </b-col>
        </b-row>
        </b-container>
        <h5>We also appreciate any contributions to our honeymoon in Key West!
        </h5>
        <a href="https://www.kwmermaid.com">
            <b-img-lazy width="200%" :src="require('../assets/mermaid&alligator_logo.jpg')"/>
        </a>
        <h5>We will be staying at the historic Mermaid and the Alligator. Gift certificates may be purchased
            <a href="https://www.kwmermaid.com/about-us/contact-us.html">here</a>
        </h5><br>
        <h5>Another thoughtful contribution would be gift certificates to Daisy Massage and Spa</h5>
        <a href="http://daisymassage.com/giftcards.asp">
          <b-img-lazy width="200%" :src="require('../assets/daisy_massage_logo.png')"/>
        </a>
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
  font-family: 'Libre Baskerville';
  text-align: center;
  font-size: 250%;
  color: #000000;
}

h5 {
  text-align: center;
  font-family: 'Libre Baskerville';
  color: #000000;
}

img {
  display:block;
  margin:auto;
  max-width:85%;
}

.subheader {
  font-family: 'Dancing Script';
  text-align: center;
  font-size: 150%;
  color: #000000;
}
</style>
