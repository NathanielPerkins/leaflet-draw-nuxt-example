<template>
  <div>
    <l-map
      style="min-height: 100vh"
      :zoom="zoom"
      :center="center"
      :options="{zoomControl: false}"
    >
      <l-draw-toolbar position="topright"/>
      <l-tile-layer :url="url"></l-tile-layer>
    </l-map>
  </div>
</template>
<script>
import { LMap, LTileLayer } from "vue2-leaflet";
import LDrawToolbar from 'vue2-leaflet-draw-toolbar';

export default {
  components: {
    LMap,
    LTileLayer,
    LDrawToolbar
  },
  data() {
    return {
      url: "http://{s}.tile.osm.org/{z}/{x}/{y}.png",
      zoom: 10,
      center: [47.31322, -1.319482]
    };
  }
};
</script>