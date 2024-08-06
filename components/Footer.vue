<template>
  <footer>
    <div>
      <div class="cont">
        <div class="links">
          <a href="https://birds.land" target="_blank">Birds.land</a>
        </div>
        <div class="about">
          <p>Discord: ebar_drakonov</p>
          <p>prod. by cobalteek</p>
        </div>
      </div>
    </div>
<!--    <div class="disclaimer">-->
<!--      <p>Не относится к Mojang Studios.</p>-->
<!--    </div>-->
  </footer>
</template>

<script setup>

</script>

<style lang="scss" scoped>
  footer {
    width: 100%;
    height: 131px;
    background: #cc1818;
    color: #e2e7e8;
    margin-top: auto;
  }

  .cont {
    margin-top: 10px;
    padding-top: 10px;
    margin-left: 10px;
    margin-right: 10px;
    display: flex;
    justify-content: space-between;
  }

  .links {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }

  //.disclaimer {
  //  padding-top: 25px;
  //  padding-left: 2059px;
  //  color: #b1b1b1
  //}
</style>