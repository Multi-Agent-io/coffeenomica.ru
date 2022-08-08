<template>
  <div class="map">
    <iframe
      ref="iframe" 
      class="footer__map"
      src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1998.9166833887862!2d30.34615831625457!3d59.933524669472924!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x469631716613151d%3A0x885e618ab88a285c!2sCoffeenomica!5e0!3m2!1sen!2sru!4v1658994514860!5m2!1sen!2sru"
      width="100%"
      height="100%"
      style="border:0;" 
      allowfullscreen="" 
      referrerpolicy="no-referrer-when-downgrade"
      @load="load" v-show="iframe.loaded">
    </iframe>
    <div class="map-image" v-show="!iframe.loaded">
      <g-image src="~/assets/images/default-map.jpg" alt="Карта, помогающая нас найти"/> 
    </div>
  </div>
</template>

<script>
export default {

  data() {
  return {
  	iframe: {
      loaded: false
    },
  }
  },

  methods: {
		load: function(){
    	this.iframe.loaded = true;
    }
  }

}
</script>

<style scoped>
 .map {
    position: relative;
    width: 55%;
    margin-left: auto;
    height: 800px;
    filter: grayscale(1);
    transition: filter .3s ease-in-out;
  
  }

  .map-image {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 11;
  }

  .map-image img {
    width: 100%;
    height: 100%;
  }
  

  iframe {
    position: relative;
    z-index: 15;
  }
  .map:hover {
    filter: grayscale(0);
  }

  /* styles for media queries */
  @media screen and (max-width: 932px) {
    .map {
      position: absolute;
      height: 514px;
      width: 100%;
      top: 31.5%;
      z-index: 10;
    }
  }

  @media screen and (max-width: 560px) {
    .map {
      height: 230px;
      top: 38.7%;
    }
  }

</style>