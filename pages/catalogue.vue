<script setup>
import sectionJSON from '../content/section_list.json'

const sections = ref()
async function fetchData() {
  sections.value = await sectionJSON.data
}
fetchData()

</script>

<template>
  <div>
    <Card
      v-if="sections"
      v-for="product in sections.array"
      :card-path = product.path
      :card-name = product.name
      :card-description = product.description
      :background-image = product.img
      :color-card = sections.colorCard
      :color-background-text = sections.colorBackgroundText
      header_text_size = "1.8vh"
      footer_text_size = "3vh"
    />
    <div class="loader" v-else><Loader/></div>
    <NuxtPage :page-key="route => route.fullPath" />
  </div>
</template>

<style lang="scss" scoped>


.loader {
  margin-top: 25vh;
}

</style>