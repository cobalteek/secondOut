<script setup>

const cards = [
  {name: "Информация", description: "Правила и всякая инфа", img: "iron_axe", path: "info"},
  {name: "Каталог", description: "Все товары и их цена", img: "iron_boots", path: "catalog"},
  {name: "Карта", description: "Поможет найти товар в нашем большом магазине!", img: "iron_chestplate", path: "map"}]
</script>

<template>
  <div class = "cont">
    <div class = "card" v-for="card in cards" :to="`/search/${card}`">
      <a :href="`${card.path}`">
      <div class = "headCard">
        <p>{{ card.name }}</p>
      </div>
      <div class="imgCard">
        <img
          :src="`/images/iron_chestplate.svg`"
          >
      </div>
      <div class="descp">
        {{ card.description }}
<!--        <img class="img"-->
<!--          :src="`/images/iron_chestplate.svg`"-->
<!--        >-->
      </div>
      </a>
    </div>
  </div>
</template>

<style scoped lang="scss">

.cont {
  width: 100%;
  padding-left: 20vw;
  padding-right: 20vw;
  display: inline-flex;
  justify-content: space-between;
  align-items: center;
  flex: 1 0 auto;
}

.card {
  margin-top: 15px;
  width: 20%;
  color: black;
  border: black 2px solid;
}

.headCard {
  display: flex;
  justify-content: center;
  align-items: center;
  border-bottom: 1px solid black;
}

.imgCard {
  display: flex;
  justify-content: center;
  align-items: center;
}

.descp.img {

}

.descp {
  display: flex;
  justify-content: center;
  align-items: center;
  border-top: black 1px solid;
}

</style>