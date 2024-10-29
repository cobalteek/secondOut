<script setup>

</script>

<template>
  <footer>
    <div class="cont">
      <div class="links transform hover:scale-105 transition duration-300">
        <a
          href="https://birds.land"
          target="_blank">
          <img
            alt="Лютий сайтик пон?"
            class=""
            src="../public/images/tool_icons/birdsLogo.svg">
        </a>
      </div>
      <div class="about">
        <p>Discord: ebar_drakonov</p>
        <a href="https://github.com/cobalteek" target="_blank">prod. by cobalteek</a>
      </div>
    </div>
    <div class="cont-disc">
      <div class="disclaimer">
        <p>Не относится к Mojang Studios.</p>
      </div>
    </div>
  </footer>
</template>

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