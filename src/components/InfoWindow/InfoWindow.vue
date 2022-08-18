<template>
  <div id="info_window_container">
    <div>信息展示：</div>
    <div>
      <span>地址：</span>
      <span>{{placeAddress}}</span>
    </div>
    <div>
      <span>坐标：</span>
      <span>{{placeLocation}}</span>
    </div>
  </div>
</template>

<script>
import bus from '@/bus/bus'
export default {
  data() {
    return {
      placeAddress: '',
      placeLocation: ''
    }
  },
  created() {
    bus.$on('shareAddressDetails', val => {
      this.placeAddress = val.address
      this.placeLocation = val.pos
    })
  }
}
</script>

<style lang="less" scoped>
#info_window_container {
  height: 150px;
  width: 300px;
  background-color: rgb(223, 223, 223);
}
</style>