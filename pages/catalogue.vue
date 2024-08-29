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
    <template v-if="!$route.path.includes('food-section') === !$route.path.includes('end-section')">
      <Card
        v-if="sections"
        v-for="product in sections.array"
        :card-path = product.path
        :card-name = product.name
        :card-description = product.description
        :background-image = product.img
        :color-card = product.colorCard
        :color-background-text = product.colorBackgroundText
        header_text_size = "1.8vh"
        footer_text_size = "3vh"
      />
      <div class="loader" v-else><Loader/></div>
    </template>
    <NuxtPage />
  </div>
</template>

<style lang="scss" scoped>

.loader {
  margin-top: 25vh;
}

</style>