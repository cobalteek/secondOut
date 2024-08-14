<script setup lang="ts">
import cardsJSON from '../json/card.json'

const cards = cardsJSON.data

</script>

<template>
  <div class="page-container">
    <Header />
    <div class="content-wrap">
      <News />
      <div class="cont">
        <Card
          v-for="card in cards.array"
          :card-path="card.path"
          :card-name="card.name"
          :img ="card.img"
          :card-description = card.description
          :color-card = card.colorCard
          :color-background-text = card.colorBackgroundText
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
