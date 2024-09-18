<script setup>
import { computed } from 'vue';
import { useRoute } from 'vue-router';
import items from '../content/outside_products.json';
import Fuse from 'fuse.js';

const route = useRoute();
const searchQuery = computed(() => {
  const query = route.query.q;

  if (Array.isArray(query)) {
    return query[0] || '';
  }

  return query || '';
});

const fuseOptions = {
  keys: ['name', 'altNames'],
  threshold: 0.25,
};

const fuse = new Fuse(items.data.slice(12), fuseOptions);

const filteredItems = computed(() => {
  const searchTerm = searchQuery.value.toLowerCase();

  if (!searchTerm) {
    return items.data;
  }

  const result = fuse.search(searchTerm);

  return result.map(res => res.item);
});

</script>

<template>
  <div>
    <h1>Результаты поиска для "{{ searchQuery }}"</h1>
    <Card
      v-for = "product in filteredItems"
      :card-name = product.name
      :card-description = product.description
      :background-image = product.img
      :bool-price = true
      :count = product.count
      :is-block = product.isBlock
      :color-card = product.colorCard
      :color-background-text = product.colorBackgroundText
      header_text_size = "1.8vh"
      footer_text_size = "3vh"
    />
    <NotFound
      v-if = 'filteredItems.length < 1'
    />
  </div>
</template>
