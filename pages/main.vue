<script setup lang="ts">
import cardsJSON from '~/content/card.json'
const cards = cardsJSON.data
</script>

<template>
  <div>
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
        header_text_size = "1.8vh"
        footer_text_size = "3vh"
      />
    </div>
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
