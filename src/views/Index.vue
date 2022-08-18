<template>
  <div id="index_container">
    <div id="search_wrap">
      <search></search>
    </div>
    <div id="map_wrap">
      <map-container></map-container>
    </div>
    <div id="heatMap_wrap">
      <heat-map-search-box></heat-map-search-box>
    </div>
    <div id="shadow">
    </div>
    <div id="info_window_wrap">
      <info-window></info-window>
    </div>
  </div>
</template>

<script>
import MapContainer from '@/components/MapContainer/MapContainer.vue'
import Search from '@/components/Search/Search.vue'
import HeatMapSearchBox from '@/components/heatMapSearchBox/heatMapSearchBox.vue'
import InfoWindow from '@/components/InfoWindow/InfoWindow.vue'
export default {
  components: { MapContainer, Search, HeatMapSearchBox, InfoWindow }
}
</script>

   
<style lang="less" scoped>
#index_container {
  overflow: hidden;
  background-color: rgb(207, 229, 248);
  height: 100%;
  width: 100%;
  position: relative;
  #map_wrap {
    z-index: 10;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    height: 60%;
    width: 60%;
  }
  #search_wrap {
    z-index: 10;
    position: absolute;
    top: 10%;
    left: 50%;
    height: 60px;
    width: 400px;
    transform: translate(-50%, -50%);
  }
  #shadow {
    height: 80%;
    width: 80%;
    position: absolute;
    top: 40%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: rgb(255, 255, 255);
  }
  #heatMap_wrap {
    z-index: 12;
    position: absolute;
    top: 15%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  #info_window_wrap {
    z-index: 100;
    position: absolute;
  }
}
</style>