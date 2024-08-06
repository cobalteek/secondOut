<script setup lang="ts">
// ваш код
</script>

<template>
  <div class="page-container">
    <Header />
    <div class="content-wrap">
      <News />
      <Card />
    </div>
    <Footer />
  </div>
</template>

<style scoped>
html, body {
  height: 100%;
  margin: 0;
}

.page-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.content-wrap {
  flex: 1;
}
</style>
