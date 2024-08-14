<template>
  <footer>
    <div class="cont">
      <div class="links">
        <a
          href="https://birds.land"
          target="_blank">
          <img
            alt=""
            class=""
            src="public/birdsLogo.svg">
        </a>
      </div>
      <div class="about">
        <p>Discord: ebar_drakonov</p>
        <p>prod. by cobalteek</p>
      </div>
    </div>
    <div class="cont-disc">
      <div class="disclaimer">
        <p>Не относится к Mojang Studios.</p>
      </div>
    </div>
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

  .cont-disc {
    display: flex;
    justify-content: flex-end;
    margin-top: 2em;
    margin-right: 10px;
  }

  .cont {
    margin-top: 10px;
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

  .disclaimer {
    color: #b1b1b1
  }
</style>