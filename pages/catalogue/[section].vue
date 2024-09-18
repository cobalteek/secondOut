<script setup lang="ts">
import prodJSON from '../../content/outside_products.json'
import { useRoute } from 'vue-router';

const route = useRoute()

const category = route.params.section

const filteredData = prodJSON.data.filter(item => item.category === category);

</script>

<template>
  <Card
    v-for = "product in filteredData"
    :card-name = product.name
    :card-description = product.description
    :background-image = product.img
    :bool-price = true
    :count = product.count
    :is-block = product.isBlock
    :color-card = product.colorCard
    :color-background-text = product.colorBackgroundText
    header_text_size = "1.8vh"
    footer_text_size = "3vh"
  />
  <NotFound
    v-if="filteredData.length <= 1"
  />
</template>

<style scoped lang="scss">


</style>

