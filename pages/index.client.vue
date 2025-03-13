<!--
<template>
    <MglMap
        :map-style=style
        :center=center
        :zoom=zoom
        height="90vh"
        width="90vw"
    >

    </MglMap>
</template>

<script setup>

const style = ref('https://api.maptiler.com/data/58844a69-0d25-4197-ad89-1e9a6a26536c/features.json?key=PwC2jocv4NVyydk2b5rt');
const center = ref([-1.559482, 47.21322]);
const zoom = ref(8);
</script>
 
 -->


<template>
  <MglMap
    :map-style="style"
    :center="center"
    :zoom="zoom"
  >
    <MglNavigationControl />
  </MglMap>
</template>

<script setup>
import { MglMap, LngLat } from 'maplibre-gl';
const style = 'https://api.maptiler.com/data/58844a69-0d25-4197-ad89-1e9a6a26536c/features.json?key=PwC2jocv4NVyydk2b5rt';
const center = [37.66034, 29.32612];
const zoom = 8;
</script>
