<script setup lang="ts">
import cardsJSON from '../json/card.json'

const cards = cardsJSON.data.array

</script>

<template>
  <div class="page-container">
    <Header />
    <div class="content-wrap">
      <News />
      <div class="cont">
        <Card
          v-for="card in cards"
          :card-path="card.path"
          :card-name="card.name"
          :img ="card.img"
          :card-description = card.description
        />
      </div>
    </div>
    <Footer />
  </div>
</template>

<style scoped>
html, body {
  height: 100%;
  margin: 0;
}

.cont {
  width: 100%;
  height: 30vh;
  display: inline-flex;
  justify-content: center;
}
</style>
