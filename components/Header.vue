<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router';

const query = ref('');
const router = useRouter();

const submitSearch = () => {
  if (query.value) {
    router.push({ name: 'searchResult', query: { q: query.value } });
  }
};


</script>

<template>
  <header class = "nav">
    <div class = "cont">
      <div class = "select-none">
        <NuxtLink to="/" class = "main-tab">Outside</NuxtLink>
      </div>
      <form class="frm" @submit.prevent="submitSearch">
        <input
          class = "inp"
          type="text"
          placeholder="Поиск"
          v-model="query"
        >
        <button
          class="btn"
          type="submit"
        >
          <img
            class="search-btn"
            alt=""
            src="../public/images/tool_icons/search16.svg">
        </button>
      </form>
    </div>
  </header>
</template>

<style scoped lang="scss">

.nav {
  display: inline-flex;
  justify-content: center;
  align-items: center;
  height: 130px;
  width: 100%;
  background-color: #cc1818;
  color: #e2e7e8;
}

.cont {
  display: inline-flex;
  justify-content: space-between;
  align-items: center;
  width: 70%;
}

.main-tab {
  font-size: 30px;
  margin-left: 15px;
}

.frm {
  display: flex;
  justify-content: center;
  margin-right: 15px;
  padding-right: 4px;
  align-items: flex-end;
  border-color: #e31d1d;
  background-color: #e2e7e8;
  border-radius: 15px;
  color: black;
}

.search-btn {
  padding-bottom: 4px;
}


.inp {
  background-color: #e2e7e8;
  padding-left: 10px;
  border-radius: 15px;
}

input[type="search"]::-webkit-search-cancel-button {
  display: none;
}

.inp:focus {
  outline: none;
}

.inp:checked {
  background-image: none;
}

</style>