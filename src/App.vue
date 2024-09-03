<template>
  <div class="app">
    <room-area :area-data="highScore"></room-area>
  </div>
</template>

<script setup>
import RoomArea from "./components/RoomArea.vue";
// import highScore from "./data/high_score.json"
import {ref} from 'vue'

const highScore = ref({})
setTimeout(() => {
  import("./data/high_score.json").then(res => {
    console.log(res.default)
    highScore.value = res.default 
  })
}, 1000)
console.log(highScore)
</script>

<style lang="less" scoped>
  .app {
    width: 1032px;
    padding: 40px;
    margin: 0 auto;
  }

  
</style>
