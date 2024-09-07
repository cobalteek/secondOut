<script setup lang="ts">

</script>

<template>
  <div>
    <h3>Ничего не найдено</h3>
    <NuxtLink to="/">
      <button>Вернуться на главную</button>
    </NuxtLink>
  </div>
</template>

<style scoped lang="scss">

div {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-top: 25%;
}

h3, button {
  font-size: 2vw;
}
button {
  background-color: #cc1818;
  color: white;
  border-radius: 10px;
}

</style>