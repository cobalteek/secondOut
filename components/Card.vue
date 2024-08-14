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

function goToLink(path) {
  if (!path) return
  router.push(path)
}

if(props.cardName.length >= 13) {
  headerTextSize.value = '21px';
}
if (props.footer_text_size == null) {
  footerTextSize.value = "32px";
}

</script>

<template>
  <div class = "cont">
    <div class = "card" :style="{'--color-card': `${props.colorCard}`}" >
      <div @click=goToLink(props.cardPath) :class="{ 'cursor-pointer': props.cardPath }">
        <div class = "card-title">
          <p
            class="backgroundText"
            :style="{'--header-text-size': `${header_text_size}`,
            '--color-background-text': `${props.colorBackgroundText}`}">
            {{ props.cardName }}</p>
        </div>
        <div class="card-content" :style="{ '--bg-image': `url(../images/${backgroundImage}.webp)`}">
          <div
            class="card-content-img">
            <img
              v-if="!props.boolPrice"
              alt=""
              :src="`/images/${props.img}.svg`">
          </div>
          <div class="card-content-p">
            <p class="count" >{{ props.count }}</p>
          </div>
        </div>
        <div class="card-footer">
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
                src="../public/images/diamond_block.webp">
              <img
                v-else
                class="diamond"
                alt=""
                src="../public/images/diamond.webp">
            </div>
          </div>
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
  width: 15.25vw;
  height: 32vh;
  overflow: hidden;
  box-sizing: border-box;
  margin-top: 15px;
  margin-bottom: 15px;
  color: black;
  background-color: var(--color-card);
  border-radius: 36px;
}

.card-title {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  height: 6vh;
  padding-top: 10px;
}

.card-content {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 20.5vh;
  width: 15.25vw;
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
  margin-top: 10px;
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
  border-radius: 33px;
  padding-left: 10px;
  padding-right: 10px;
}

.backgroundText {
  display: flex;
  background-color: var(--color-background-text);
  border-radius: 36px;
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
  text-shadow: 5px 5px #3f3f3f;
  font-weight: revert;
  font-size: 3.25vh;
  padding: 25px;
}

.diamond {
  width: 40px;
  padding: 2px 0 4px 0;
}

.diamond-block {
  width: 40px;
  padding: 4px 0 4px 0;
}

@media (max-width: 600px) {
  .card {
    width: 100%;
    height: auto;
  }
}

</style>
