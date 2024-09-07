<script setup>
import { ref } from 'vue';
import { marked } from 'marked';
import axios from 'axios';

// Переменные с данными
const markdownContent = ref('');
const htmlContent = ref('');

// Функция для загрузки markdown файла и его преобразования в HTML
const loadMarkdown = async () => {
  try {
    const response = await axios.get('news.md');
    markdownContent.value = response.data;
    htmlContent.value = marked(markdownContent.value);
  } catch (error) {
    console.error('Error loading markdown file:', error);
  }
};

loadMarkdown();
</script>

<template>
  <div class="news-content">
    <div
      class="text"
      v-html="htmlContent"
      v-if="htmlContent"
    />
    <Loader class="text" v-else/>
  </div>
</template>


<style lang="scss" scoped>
  .news-content {
    margin-left: 9%;
    min-height: 30vh;
    width: 81%;
  }

  h1, h2, h3, h4, h5, h6 {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .text {
    font-size: 1.5em;
    margin-top: 3px;
    padding-top: 3%;
    padding-bottom: 3%;
  }

</style>