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
        @load="onMapLoaded"
      >
        <MglGeolocateControl ref="geolocateControl" />
      </MglMap>
    </no-ssr>
  </div>
</template>

<script>
// import Mapbox from 'mapbox-gl-vue'
 
// export default {
//   components: { Mapbox },
// }
</script>

<style>
#map {
  width: 100%;
  height: 100vh;
}
</style>