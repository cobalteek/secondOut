<script setup>
import endJSON from '@/content/end_products.json'

const endProducts = ref()
async function fetchData() {
  endProducts.value = await endJSON.data
}
fetchData()

</script>

<template>
  <div>
    <Card
      v-if="endProducts"
      v-for="product in endProducts.array"
      :card-name = product.name
      :card-description = product.description
      :background-image = product.img
      :bool-price = true
      :is-block = product.isBlock
      :count = product.count
      :color-card = endProducts.colorCard
      :color-background-text = endProducts.colorBackgroundText
      header_text_size = "1.8vh"
      footer_text_size = "3vh"
    />
    <div class="loader" v-else><Loader/></div>
  </div>
</template>

<style lang="scss" scoped>

.content-wrap {
  width: 70%;
  flex: 1;
}

.loader {
  margin-top: 25vh;
}

</style>