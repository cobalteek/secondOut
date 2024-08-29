<script setup>
import foodJSON from '@/content/food_products.json'

const foodProducts = ref()
async function fetchData() {
  foodProducts.value = await foodJSON.data
}
fetchData()

</script>

<template>
  <div>
      <Card
        v-if="foodProducts"
        v-for="product in foodProducts.array"
        :card-name = product.name
        :card-description = product.description
        :background-image = product.img
        :bool-price = true
        :is-block = product.isBlock
        :count = product.count
        :color-card = foodProducts.colorCard
        :color-background-text = foodProducts.colorBackgroundText
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