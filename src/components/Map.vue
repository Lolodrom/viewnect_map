<template>
  <div>
    <l-map class="min-h-screen z-10" :zoom="zoom" :center="center">
      <l-tile-layer :url="url"></l-tile-layer>
      <l-marker v-for="marker in markers" :key :lat-lng="marker.markerLatLng"></l-marker>
    </l-map>
  </div>
</template>

<script>
import { LMap, LTileLayer, LMarker } from "vue2-leaflet";
import L from "leaflet";

delete L.Icon.Default.prototype._getIconUrl;
L.Icon.Default.imagePath = "";
L.Icon.Default.mergeOptions({
  iconRetinaUrl:
    "https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.3.1/images/marker-icon-2x.png",
  iconUrl:
    "https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.3.1/images/marker-icon.png",
  shadowUrl:
    "https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.3.1/images/marker-shadow.png"
});

export default {
  components: {
    LMap,
    LTileLayer,
    LMarker
  },
  data() {
    return {
      url: "http://{s}.tile.osm.org/{z}/{x}/{y}.png",
      zoom: 12,
      center: [47.31322, -1.319482],
      markers: [
        { markerLatLng: { lat: 47.555759, lng: 16.08997 } },
        { markerLatLng: { lat: 47.70286, lng: 16.03352 } },
        { markerLatLng: { lat: 47.5238, lng: 16.19257 } }
      ]
    };
  }
};
</script>

<style>
</style>