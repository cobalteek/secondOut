<script setup>
  const router = useRouter()

  const headerTextSize = ref('--header-text-size')
  const footerTextSize = ref('--footer-text-size')

  const props = defineProps({
    cardName: String,
    altNames: String,
    cardDescription: String,
    cardPath: String,
    img: String,
    boolPrice: Boolean,
    isBlock: Boolean,
    count: String,
    backgroundImage: String,
    header_text_size: String,
    footer_text_size: String,
    colorCard: String,
    colorBackgroundText: String,
    min_height: String,
    min_width: String
  })
  

</script>

<template>
  <div class = "cont">
    <div class = "card" :style="{'--color-card': `${props.colorCard}`}" >
      <NuxtLink :to="props.cardPath">
        <div class = "card-title">
          <p
            class="backgroundText"
            :style="{'--header-text-size': `${header_text_size}`,
            '--color-background-text': `${props.colorBackgroundText}`}">
            {{ props.cardName }}</p>
        </div>
        <div class="card-content" :style="{ '--bg-image': `url(../images/${backgroundImage}.webp)`}">
          <div class="card-content-p">
            <p class="count" >{{ props.count }}</p>
          </div>
        </div>
        <div v-if=props.cardDescription class="card-footer">
          <div class="card-price" :style="{'--color-background-text': `${props.colorBackgroundText}`}">
            <p
              v-if="props.boolPrice"
              class="backgroundPrice"
              :style="{'--footer-text-size': `${footer_text_size}`}"
            >
              {{ props.cardDescription }}
            </p>
            <div v-if="props.boolPrice">
              <img
                v-if="props.isBlock"
                class="diamond-block"
                alt=""
                src="../public/images/tool_icons/diamond_block.webp">
              <img
                v-else
                class="diamond"
                alt=""
                src="../public/images/tool_icons/diamond.webp">
            </div>
          </div>
        </div>
      </NuxtLink>
    </div>
  </div>
</template>

<style scoped lang="scss">

.cont {
  display: inline-flex;
  justify-content: space-between;
  align-items: center;
  margin-right: 1.25vw;
}

.card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 16vw;
  height: 32vh;
  overflow: hidden;
  box-sizing: border-box;
  margin-top: 15px;
  margin-bottom: 15px;
  color: black;
  background-color: var(--color-card);
  border-radius: 3vh;
}

.card-title {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  height: 6vh;
  width: 100%;
  padding-top: 10px;
}

.card-content {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 20.5vh;
  width: 15.25vw;
  margin-left: 0.35vw;
  background-image: var(--bg-image);
  background-size: 20.5vh;
  background-position: center;
  background-repeat: no-repeat;
}

.card-content-p {
  display: flex;
  justify-content: flex-end;
  align-items: flex-end;
  min-height: 15.4vh;
  min-width: 12.7vw;
  margin-top: 1vw;
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
  line-height: normal;
  height: 5.5vh;
}

.card-price {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: var(--color-background-text);
  border-radius: 3vh;
  padding-left: 10px;
  padding-right: 10px;
}

.backgroundText {
  display: flex;
  background-color: var(--color-background-text);
  border-radius: 3vh;
  padding-left: 5px;
  padding-right: 5px;
  font-size: var(--header-text-size);
}

.backgroundPrice {
  display: inline-block;
  padding: 0 5px 0 5px;
  border-radius: 10px;
  font-size: var(--footer-text-size);
}

.count {
  font-family: "Minecraft Rus", sans-serif;
  color: white;
  text-shadow: 0.4vh 0.4vh #3f3f3f;
  font-weight: revert;
  font-size: 3.25vh;
  padding: 1.25vw;
}

.diamond {
  width: 2.3vw;
  padding: 2px 0 4px 0;
}

.diamond-block {
  width: 2.2vw;
  padding: 4px 0 4px 0;
}

@media (max-width: 600px) {

}

</style>
