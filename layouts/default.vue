<script setup lang="ts">

</script>

<template>
  <div class="page-container">
    <Header />
    <main class="content-wrap">
      <slot />
    </main>
    <Footer />
  </div>
</template>

<style lang="scss">

main {
  padding: 0;
  margin: 0;
}

</style>
