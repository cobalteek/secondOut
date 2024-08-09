<script setup>

const router = useRouter()

const props = defineProps({
  cardName: String,
  altNames: String,
  cardDescription: String,
  cardPath: String,
  img: String,
  boolPrice: Boolean
})

function goToLink(path) {
  if (!path) return
  router.push(path)
}

const price = ref("Цена: ")

</script>

<template>
  <div class = "cont">
    <div class = "card" >
      <div @click=goToLink(props.cardPath) :class="{ 'cursor-pointer': props.cardPath }">
        <div class = "card-title">
          <p>{{ props.cardName }}</p>
        </div>
        <div class="card-content">
          <img alt=""
            :src="`/images/${props.img}.svg`">
        </div>
        <div class="card-footer">
          <p v-if="props.boolPrice">{{ price }}</p>
          <p>{{ props.cardDescription }}</p>
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
  margin-right: 83px;
  margin-left: 99px;
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
  border: #000000 2px solid;
}

.card-title {
  display: flex;
  justify-content: center;
  align-items: center;
  border-bottom: 1px solid #000000;
  padding: 10px;
}

.card-content {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-grow: 1;
}

.card-content img {
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
}

.card-footer {
  display: flex;
  justify-content: center;
  align-items: center;
  border-top: #000000 1px solid;
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
