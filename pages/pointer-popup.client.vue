<template>
<div min-height="500px">
    <mgl-map
    :map-style="style"
    :center="center"
    :zoom="zoom"
    height="500px"
  >
    <mgl-navigation-control />
    <mgl-marker :coordinates="coordinates">
      <mgl-popup ref="popup" @open="console.log('popup opened')" max-width="200px">
        <h1>Hello</h1>
        <p>HTML content</p>
        <a href="#" @click.prevent="closePopup">Close popup</a>
      </mgl-popup>
    </mgl-marker>
  </mgl-map>
</div>
</template>

<script setup>
import {
  MglMap,
  MglNavigationControl,
  MglMarker,
  MglPopup,
} from '@indoorequal/vue-maplibre-gl';
import { useTemplateRef } from 'vue'

const style = ref('https://api.maptiler.com/maps/streets/style.json?key=cQX2iET1gmOW38bedbUh');
const center = [12.550343, 55.665957];
const zoom = 8;
const coordinates = [12.550343, 55.665957];

const popupRef = useTemplateRef('popup')
const closePopup = () => {
  popupRef.value.remove()
};

</script>