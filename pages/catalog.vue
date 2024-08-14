<script setup>
import endJSON from '../json/end_products.json'
import foodJSON from '../json/food_products.json'

const endProudcts = ref()
const foodProducts = ref()
async function fetchData() {
  endProudcts.value = await endJSON.data
  foodProducts.value = await foodJSON.data
}


fetchData()

</script>

<template>
  <div class="page-container">
    <Header/>
    <div class="content-wrap">
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
      <div v-else>Загрузка</div>
    </div>
    <Footer/>
  </div>
</template>

<style lang="scss" scoped>

.content-wrap {
  width: 70%;
  flex: 1;
}

</style>