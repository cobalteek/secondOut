<template>
  <div class="loader">
    <img class="img-loader" src="../public/images/tool_icons/ender_chest.webp" alt="">
    <p class="text-loader">{{load}}</p>
  </div>
</template>

<script setup>
let load = 'Loading'
</script>

<style lang="scss" scoped>
.loader {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.img-loader {
  height: 20vh;
}

.text-loader {
  font-size: 2.5vh;
}
</style>