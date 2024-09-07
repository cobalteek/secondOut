<script setup>
import sectionJSON from '../../content/outside_products.json'

const sections = ref('sections')

const filteredData = sectionJSON.data.filter(item => item.category === sections.value);

</script>

<template>
  <Card
    v-if = filteredData
    v-for="product in filteredData"
    :card-path = product.path
    :card-name = product.name
    :card-description = product.description
    :background-image = product.img
    :color-card = product.colorCard
    :color-background-text = product.colorBackgroundText
    header_text_size = "1.8vh"
    footer_text_size = "3vh"
  />
  <Loader class="loader" v-else/>
</template>

<style lang="scss" scoped>

.loader {
  margin-top: 25vh;
}

</style>