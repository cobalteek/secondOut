<script setup>

const router = useRouter()

const props = defineProps({
  cardName: String,
  altNames: String,
  cardDescription: String,
  cardPath: String,
  img: String,
  boolPrice: Boolean,
  count: String,
  backgroundImage: String
})

function goToLink(path) {
  if (!path) return
  router.push(path)
}

</script>

<template>
  <div class = "cont">
    <div class = "card" >
      <div @click=goToLink(props.cardPath) :class="{ 'cursor-pointer': props.cardPath }">
        <div class = "card-title">
          <p class="backgroundText" >{{ props.cardName }}</p>
        </div>
        <div class="card-content" :style="{ '--bg-image': `url(../images/${backgroundImage}.svg)` }">
<!--          <img-->
<!--            alt=""-->
<!--            :src="`/images/${props.img}.svg`">-->
          <p class="count" >{{ props.count }}</p>
        </div>
        <div class="card-footer">
          <p class="backgroundPrice">{{ props.cardDescription }}</p>
          <img
            class="diamond"
            v-if="props.boolPrice"
            alt=""
            src="../public/images/diamond.svg">
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">

.cont {
  display: inline-flex;
  justify-content: space-between;
  align-items: center;
  margin-right: 50px;
  margin-left: 50px;
}

.card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 250px;
  height: 350px;
  overflow: hidden;
  box-sizing: border-box;
  margin-top: 15px;
  margin-bottom: 15px;
  color: black;
  background-color: rgba(204, 160, 186, 0.75);
  border-radius: 33px;
}

.card-title {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 10px;
}

.backgroundText {
  display: inline-block;
  padding: 0 5px 0 5px;
  background-color: #B790A7;
  border-radius: 10px;
}

.backgroundPrice {
  display: inline-block;
  padding: 0 5px 0 5px;
  background-color: #B790A7;
  border-radius: 10px;
}

.card-content {
  display: flex;
  justify-content: flex-end;
  align-items: flex-end;
  min-height: 200px;
  min-width: 250px;
  margin-top: 10px;
  background-image: var(--bg-image);
  background-size: 200px;
  background-position: center;
  background-repeat: no-repeat;
  flex-grow: 1;
}

.count {
  font-family: "Minecraft Rus", sans-serif;
  color: white;
  text-shadow: 5px 5px #3f3f3f;
  font-weight: revert;
  font-size: 42px;
  padding: 25px;
}

.diamond {
  width: 32px;
  padding-bottom: 2px;
}

.card-footer {
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 32px;
  padding: 10px;
  height: auto;
  line-height: normal;
  min-height: 60px;
}

@media (max-width: 600px) {
  .card {
    width: 100%;
    height: auto;
  }
}

</style>
