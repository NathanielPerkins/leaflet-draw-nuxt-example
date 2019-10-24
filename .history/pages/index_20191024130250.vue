<template>
  <div
    class="map"
  >
    <no-ssr>
      <MglMap
        :access-token="pk.eyJ1IjoibmF0aGFuanAiLCJhIjoiY2syM3UxYnUyMDBsYjNocGVjZHZzdGF6OCJ9.O-PIAgQOzeHjRNzoNq8mEQ"
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

</script>

<style>
#map {
  width: 100%;
  height: 100vh;
}
</style>