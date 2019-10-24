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
import '@geoman-io/leaflet-geoman-free';

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
      map.pm.addControls({
        drawMarker: false,
        drawPolygon: true,
        editPolygon: true,
        drawPolyline: false,
        deleteLayer: true
      });
      // console.log(map);
      // const drawControl = new window.L.Control.Draw({
      //   position: 'topleft',
      //   draw: {
      //     polyline: {
      //       allowIntersection: false,
      //       showArea: true,
      //       edit: true
      //     },
      //     polygon: false,
      //     rectangle: false,
      //     circle: false,
      //     marker: false,
      //     circlemarker: false
      //   }
      // });

      // map.addControl(drawControl);
      // let editActions = [
      //   L.Toolbar2.EditAction.Popup.Edit,
      //   L.Toolbar2.EditAction.Popup.Delete,
      //   // L.Toolbar2.Action.extendOptions({
      //   //   toolbarIcon: { 
      //   //     className: 'leaflet-color-picker', 
      //   //     html: '<i class="fas fa-fill-drip"></i>' 
      //   //   },
      //   //   subToolbar: new L.Toolbar2({ actions: [
      //   //     L.ColorPicker.extendOptions({ color: '#db1d0f' }),
      //   //     L.ColorPicker.extendOptions({ color: '#025100' }),
      //   //     L.ColorPicker.extendOptions({ color: '#ffff00' }),
      //   //     L.ColorPicker.extendOptions({ color: '#0000ff' })
      //   //   ]})
      //   // })
      // ];
      // const editableLayers = new window.L.FeatureGroup().addTo(map);
      // map.on(window.L.Draw.Event.CREATED, (e) => {
      //   // const type = e.layerType;
      //   const layer = e.layer;

      //   layer.on('click', function(event) {
      //     this.editMode = true
      //     new L.Toolbar2.EditToolbar.Popup(event.latlng, {
      //       actions: editActions
      //     }).addTo(map, layer);
      //   });
      //   layer.addTo(map);
      //   // Do whatever else you need to. (save to db, add to map etc)
      //   // editableLayers.addLayer(layer);
      // });
    });
  }
};
</script>