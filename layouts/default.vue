<script setup lang="ts">

</script>

<template>
  <div class="page-container">
    <Header />
    <div class="content-wrap">
      <main>
        <slot />
      </main>
    </div>
    <Footer />
  </div>
</template>

<style lang="scss">

main {
  padding: 0;
  margin: 0;
}

</style>
