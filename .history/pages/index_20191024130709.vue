<template>
  <div
    class="map"
  >
    <no-ssr>
      <MglMap
        :access-token=""
        :map-style="mapStyle"
        :center="center"
        :zoom="zoom"
        @load="onMapLoaded"
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
            "access-token": "pk.eyJ1IjoibmF0aGFuanAiLCJhIjoiY2syM3UxYnUyMDBsYjNocGVjZHZzdGF6OCJ9.O-PIAgQOzeHjRNzoNq8mEQ"
        }
    }
}
</script>

<style>
#map {
  width: 100%;
  height: 100vh;
}
</style>