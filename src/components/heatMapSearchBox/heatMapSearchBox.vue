<template>
  <div id="heat_map_search_box_container">
    <el-checkbox v-model="checked" @change="send">热力图显示</el-checkbox>
  </div>
</template>

<script>
import bus from '@/bus/bus'
export default {
  data() {
    return {
      checked: false
    }
  },
  methods: {
    send() {
      bus.$emit('shareHeatMapShow', this.checked)
    }
  }
}
</script>

<style lang="less" scoped>
#heat_map_search_box_container {
  height: 100%;
  width: 100%;
  position: relative;
}
</style>