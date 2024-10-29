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
  <div class="news-content prose prose-lg">
    <div
      class="text"
      v-html="htmlContent"
      v-if="htmlContent"
    />
    <Loader class="text" v-else />
  </div>
</template>

<style lang="scss" scoped>
  .news-content {
    min-height: 30vh;
    width: 100%;
  }

  .text {
    font-size: 20px;
    margin-top: 3px;
    padding-top: 3%;
    padding-bottom: 3%;
  }


  @media (max-width: 375px) {
    .text {
      font-size: 18px;
    }
  }
  @media (max-width: 600px) {
    .text {
      font-size: 18px;
    }
  }
  @media (max-width: 960px) {
    .text {
      font-size: 18px;
    }
  }

</style>