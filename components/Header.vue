<script setup>

</script>

<template>
  <div class = "nav">
    <div class = "select-none">
      <a href="http://localhost:3000" class = "main-tab">Outside</a>
    </div>
    <form class="frm" action="">
      <input class = "inp" type="search" placeholder="Поиск товаров" >
    </form>
  </div>
</template>

<style scoped lang="scss">

.nav {
  display: inline-flex;
  justify-content: space-between;
  align-items: center;
  height: 75px;
  width: 60%;
  margin-left: 20%;
  background-color: #b71a1a;
  color: #e2e7e8;
}

.main-tab {
  font-size: 30px;
  margin-left: 15px;
}

.frm {
  margin-right: 15px;
  align-items: flex-end;
  border-color: #e31d1d;
  border-radius: 3px;
  color: black;
}

.btn {
  background-color: #e2e7e8;
  border: white 0;
}

.inp {
  background-color: #e2e7e8;
}
.inp:focus {
  outline: none;
}

</style>