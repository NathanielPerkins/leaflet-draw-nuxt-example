<template>
	<client-only>
    <l-map></l-map>
  </client-only>
</template>

<script>
	export default {
		name: 'leaflet-map',
		mounted() {
			var mymap = L.map('map-wrap').setView([51.505, -0.09], 13)
			L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibmF0aGFuanAiLCJhIjoiY2syM3UxYnUyMDBsYjNocGVjZHZzdGF6OCJ9.O-PIAgQOzeHjRNzoNq8mEQ', {
        attribution: 'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
        maxZoom: 18,
        id: 'mapbox.streets',
        accessToken: 'pk.eyJ1IjoibmF0aGFuanAiLCJhIjoiY2syM3UxYnUyMDBsYjNocGVjZHZzdGF6OCJ9.O-PIAgQOzeHjRNzoNq8mEQ'
      }).addTo(mymap);
		}
}
</script>
