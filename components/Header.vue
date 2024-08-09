<script setup>
</script>

<template>
  <header class = "nav">
    <div class = "cont">
      <div class = "select-none">
        <a href="/main" class = "main-tab">Outside</a>
      </div>
      <form class="frm" action="">
        <input class = "inp" type="search" placeholder="Поиск" >
        <button @click=""> </button>
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
  margin-right: 15px;
  align-items: flex-end;
  border-color: #e31d1d;
  color: black;
}

.btn {
  background-color: #e2e7e8;
  border: white 0;
}


.inp {
  background-color: #e2e7e8;
  padding-left: 10px;
  border-radius: 15px;
  background-image: url("../public/images/search16.svg");
  background-repeat: no-repeat;
  background-position: center right 5px;
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