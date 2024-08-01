<script setup lang="ts">
</script>

<template>
  <div class="flex flex-col">
    <main>
      <slot />
    </main>
  </div>
</template>

<style lang="scss">
main {
  padding: 16px;
  display: block;
  flex: 1;
  flex-basis: auto;
  overflow: auto;
}
</style>
