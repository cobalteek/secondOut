<script setup>
import endJSON from '../json/end_products.json'

const endProudcts = endJSON.data.array

</script>

<template>
  <div class="page-container">
    <Header/>
    <div class="content-wrap">
      <Card
        v-for="product in endProudcts"
        :card-name = product.name
        :card-description = product.description
        :img = product.img
        :bool-price = true
      />
    </div>
    <Footer/>
  </div>
</template>

<style lang="scss" scoped>

.add {
  margin: 0 5px 0 5px;
}

.content-wrap {
  width: 70%;
  flex: 1;
}

</style>