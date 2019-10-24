<template>
  <div id="app">
    <mapbox
      access-token="pk.eyJ1IjoibmF0aGFuanAiLCJhIjoiY2syM3UxYnUyMDBsYjNocGVjZHZzdGF6OCJ9.O-PIAgQOzeHjRNzoNq8mEQ"
      :map-options="{
        style: 'mapbox://styles/mapbox/light-v9',
        center: [144.9631, -37.8136],
        zoom: 10,
      }"
    />
  </div>
</template>

<script>
import Mapbox from 'mapbox-gl-vue'
 
export default {
  components: { Mapbox },
}
</script>

<style>
#map {
  width: 100%;
  height: 100vh;
}
</style>