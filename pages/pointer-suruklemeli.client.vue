<template>
  <mgl-map
    :map-style="style"
    :center="center"
    :zoom="zoom"
    height="300px"
  >
    <mgl-navigation-control />
    <mgl-marker
      v-model:coordinates="coordinates"
      :draggable="draggable"
      @dragstart="console.log('dragstart')"
      @drag="console.log('drag')"
      @dragend="console.log('dragend')"
    />
  </mgl-map>
  <label><input type="checkbox" v-model="draggable" />Enable draggable marker</label>
  <br />
  Marker coordinates: {{ coordinates }}
</template>

<script setup>
import {
  MglMap,
  MglNavigationControl,
  MglMarker
} from '@indoorequal/vue-maplibre-gl';

const style = ref('https://api.maptiler.com/maps/streets/style.json?key=cQX2iET1gmOW38bedbUh');
const center = [29.09201745022932, 37.784419858861554];
const zoom = 8;
const coordinates = ref([29.09201745022932, 37.784419858861554]);
const draggable = ref(true);
</script>
