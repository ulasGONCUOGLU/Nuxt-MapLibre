<template>
  <mgl-map
    :map-style="style"
    :center="coordinates"
    :zoom="zoom"
    height="500px"
  >
    <mgl-marker :coordinates>
      <template v-slot:marker>
        <div :style="{ backgroundColor: 'red', width: '10px', height: '10px' }"></div>
      </template>
    </mgl-marker>
  </mgl-map>
</template>

<script setup>
import {
  MglMap,
  MglMarker
} from '@indoorequal/vue-maplibre-gl';

const style = ref('https://api.maptiler.com/maps/streets/style.json?key=cQX2iET1gmOW38bedbUh');
const center = [30.550343, 38.665957];
const zoom = 15;
const coordinates = [29.1, 37.8];
</script>
