<template>
  <div>
    <l-map ref='map'
      style="min-height: 100vh"
      :zoom="zoom"
      :center="center"
      :options="{zoomControl: false}"
    >
      <!-- <l-draw-toolbar position="topright"/> -->
      <l-tile-layer :url="url"></l-tile-layer>
    </l-map>
  </div>
</template>
<script>
import { LMap, LTileLayer } from "vue2-leaflet";
import LDraw from 'leaflet-draw';
// import LDrawToolbar from 'vue2-leaflet-draw-toolbar';

export default {
  components: {
    LMap,
    LTileLayer,
    // LDrawToolbar
  },
  data() {
    return {
      url: "http://{s}.tile.osm.org/{z}/{x}/{y}.png",
      zoom: 10,
      center: [47.31322, -1.319482]
    };
  },
  mounted() {
    this.$nextTick(() => {
      const map = this.$refs.map.mapObject;
      console.log(map);
      const drawControl = new window.L.Control.Draw({
        position: 'topleft',
        draw: {
          polyline: {
            allowIntersection: false,
            showArea: true
          },
          polygon: false,
          rectangle: false,
          circle: false,
          marker: false,
          circlemarker: false
        }
      });

      map.addControl(drawControl);

      const editableLayers = new window.L.FeatureGroup().addTo(map);
      map.on(window.L.Draw.Event.CREATED, (e) => {
        // const type = e.layerType;
        const layer = e.layer;

        // Do whatever else you need to. (save to db, add to map etc)
        editableLayers.addLayer(layer);
      });
    });
  }
};
</script>