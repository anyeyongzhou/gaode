<template>
  <div id="search_container">
    <el-input v-model="inputObject.userInput" :id="inputObject.inputId" placeholder="请输入你要查找的关键词" type="text"></el-input>
    <!-- <input type="text" placeholder="" > -->
    <el-button type="primary" id="searchBtn" @click="send">search</el-button>
  </div>
</template>

<script>
import bus from '@/bus/bus'
export default {
  data() {
    return {
      inputObject: {
        userInput: '',
        inputId: 'searchInput'
      }
    }
  },
  methods: {
    send() {
      bus.$emit('shareUserInput', this.inputObject)
    }
  },
  mounted() {
    this.send()
  }
}
</script>

<style lang="less" scoped>
#search_container {
  height: 100%;
  width: 100%;
  display: flex;
  justify-content: baseline;
  align-items: center;
  #searchInput {
    height: 30px;
    width: 300px;
  }
  #searchBtn {
    // height: 30px;
    width: 100px;
  }
}
</style>