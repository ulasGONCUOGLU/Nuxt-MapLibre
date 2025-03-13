<template>
  <mgl-map
    :map-style="style"
    :center="center"
    :zoom="zoom"
    :pitch="pitch"
    height="500px"
  >
    <MglRasterDemSource
      source-id="terrain"
      url="https://demotiles.maplibre.org/terrain-tiles/tiles.json"
      :tile-size="256"
    >
    </MglRasterDemSource>
    <MglRasterDemSource
      source-id="hillshade"
      url="https://demotiles.maplibre.org/terrain-tiles/tiles.json"
      :tile-size="256"
    >
      <MglHillshadeLayer
        layer-id="hills"
        :paint="{'hillshade-shadow-color': '#473B24'}" />
    </MglRasterDemSource>

    <mgl-navigation-control
      :visualize-pitch="true"
    />
    <custom-terrain-control />
  </mgl-map>
</template>


<!-- 
Arazi muhabbeti json dosyası ile dağların kordinatları veriliyor ve bu kordinatlar doğrultusunda haritaya ekleniyor. içeriğine baktığımızda png fotoları bulunduğunu gördüm.
Şimdi ana problem şu, bu png fotoları nasıl haritaya ekleyeceğim. terrain ve hillshade biri açıyor biri kapatıyor, bunlar arasında bir bağlantı kuramadım.
-->


<script setup>
import { defineComponent } from 'vue';
import {
  MglMap,
  MglRasterDemSource,
  MglHillshadeLayer,
  MglNavigationControl,
  useControl,
} from '@indoorequal/vue-maplibre-gl';
import { TerrainControl } from 'maplibre-gl';

const style = ref('https://api.maptiler.com/maps/streets/style.json?key=cQX2iET1gmOW38bedbUh');
const center = [11.39085, 47.27574];
const zoom = 12;
const pitch = 70;

const CustomTerrainControl = defineComponent({
  setup() {
    return useControl(
      () => {
        return new TerrainControl({
           source: 'terrain',
           exaggeration: 1
        });
      }, {
        position: 'top-right'
      });
  },

  render() {
    return null;
  }
});
</script>
