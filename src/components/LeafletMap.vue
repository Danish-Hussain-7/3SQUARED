<template>
    <div class="leaflet_map">
        <l-map style="height: 300px" :zoom="zoom" :center="center">
            <l-tile-layer :url="url" :attribution="attribution"></l-tile-layer>
            <l-marker
                :key="index"
                v-for="(loc, index) in locations"
                :lat-lng="latLng(loc.lat, loc.long)">
            </l-marker>
        </l-map>
    </div>
</template>
  
<script>
export default {
    name: 'LeafletMap',
    components: {
        LMap,
        LTileLayer,
        LMarker,
    },
    data () {
        return {
            url: 'https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
            attribution: '&copy; <a target="_blank" href="http://osm.org/copyright">OpenStreetMap</a> contributors', // Required
        };
    },
    props: {
        zoom: Number,
        center: Array,
        locations: Array,
    },
    methods: {
        latLng: function(lat, long){
            return L.latLng(lat, long)
        }
    }
}

import { LMap, LTileLayer, LMarker } from 'vue2-leaflet';
import { Icon } from 'leaflet';
import L from 'leaflet';

delete Icon.Default.prototype._getIconUrl;
Icon.Default.mergeOptions({
  iconRetinaUrl: require('leaflet/dist/images/marker-icon-2x.png'),
  iconUrl: require('leaflet/dist/images/marker-icon.png'),
  shadowUrl: require('leaflet/dist/images/marker-shadow.png'),
});
</script>
  
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  
</style>
  