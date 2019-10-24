<template>
  <div
    class="map"
  >
    <no-ssr>
      <MglMap
        :access-token="accessToken"
        :map-style="mapStyle"
        :center="center"
        :zoom="zoom"
      >
        <MglGeolocateControl ref="geolocateControl" />
      </MglMap>
    </no-ssr>
  </div>
</template>

<script>
import { MglMap, MglGeolocateControl } from 'vue-mapbox';

export default {
    components: {
        MglMap,
        MglGeolocateControl
    },
    data() {
        return {
            mapStyle: "mapbox://styles/mapbox/streets-v11",
            accessToken: "pk.eyJ1IjoibmF0aGFuanAiLCJhIjoiY2syM3UxYnUyMDBsYjNocGVjZHZzdGF6OCJ9.O-PIAgQOzeHjRNzoNq8mEQ",
            zoom: 3,
            center: [144.9631, -37.8136]
        }
    },
    // head() {
    //     return {
    //         link: [{
    //             href: "https://api.tiles.mapbox.com/mapbox-gl-js/v0.53.0/mapbox-gl.css",
    //             rel: "stylesheet"
    //         }]
    //     }
    // }
}
</script>

<style>
#map {
  width: 100%;
  height: 100vh;
}
</style>