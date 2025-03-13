<template>
    <mgl-map
        :map-style="style"
        :center="center"
        :zoom="zoom"
        height="500px"
    >
        <mgl-vector-source
            source-id="libraries"
            :tiles="librariesSourceTiles"
        >
            <mgl-circle-layer
                layer-id="libraries"
                source-layer="libraries"
                :paint="librariesLayerCirclesPaint"
            />
        </mgl-vector-source>

    </mgl-map>
</template>

<script setup lang="ts">
import {
  MglMap,
  MglVectorSource,
  MglCircleLayer
} from '@indoorequal/vue-maplibre-gl';
import { CircleLayerSpecification, LineLayerSpecification, LngLatLike, MapLayerMouseEvent } from 'maplibre-gl';

const style = ref('https://api.maptiler.com/maps/streets/style.json?key=cQX2iET1gmOW38bedbUh');
const center = [11.39085, 47.27574];
const zoom = 12;

const librariesSourceTiles = [ 'https://api.librarydata.uk/libraries/{z}/{x}/{y}.mvt' ];
const librariesLayerCirclesPaint = {
  'circle-radius': 5,
  'circle-color' : '#1b5e20'
} as CircleLayerSpecification['paint'];
</script>
