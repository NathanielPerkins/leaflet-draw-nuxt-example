<template>
  <MglMap :accessToken="accessToken" :mapStyle="mapStyle"/>
</template>

<script>
import Mapbox from "mapbox-gl";
import { MglMap } from "vue-mapbox";
// import MapboxDraw from '@mapbox/mapbox-gl-draw';

export default {
  components: {
    MglMap
  },
  data() {
    return {
      accessToken: "pk.eyJ1IjoibmF0aGFuanAiLCJhIjoiY2syM3UxYnUyMDBsYjNocGVjZHZzdGF6OCJ9.O-PIAgQOzeHjRNzoNq8mEQ", // your access token. Needed if you using Mapbox maps
      mapStyle: "mapbox://styles/mapbox/streets-v11" // your map style
    };
  },

  created() {
    // We need to set mapbox-gl library here in order to use it in template
    this.mapbox = Mapbox;
  }
};
</script>

<style>

</style>
