<template>
  <h1>Wish list</h1>
  <app-card
    v-for="(item, index) in cards"
    :key="item.id"
    :card="item"
    :click="openModal"
    :index="index"
    @click="emit('click-by-card', item)"
  />
</template>

<script setup>
import { ref } from "vue";
import AppCard from "./AppCard.vue";

const props = defineProps({
  cards: {
    type: Array,
  },
  openModal: {
    type: Boolean,
  },
});

const emit = defineEmits(["click-by-card"]);
</script>

<style scoped>
.form {
  margin-bottom: 12px;
}

input {
  margin-left: 4px;
  margin-bottom: 8px;
}
</style>
