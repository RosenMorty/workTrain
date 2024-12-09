<template>
  <h1>Wish list</h1>
  <app-card
    v-for="(item, index) in cards"
    :key="item.id"
    :card="item"
    :index="index"
    class="card"
  />
</template>

<script setup>
import { ref } from "vue";
import AppCard from "./AppCard.vue";

const cards = ref([
  {
    title: "Python-разработчик",
    description:
      "Описание: На Python пишкт сайты, приложения, игры и чат-боты. Netflix, Spotify, Google и Youtube написаны на Python.",
    course_duration: "10 месяцев",
    completed: true,
  },
  {
    title: "Графический дизайнер",
    description:
      "Описание: Научим делать бренды узнаваемымми через создание логотипов, графики для рекламы, упаковки и не только.",
    course_duration: "6 месяцев",
    completed: true,
  },
  {
    title: "Веб-разработчик",
    description:
      "Описание: Веб-разработчик создает сайты, сервисы и приложения, которыми мы ежедневно пользуемся.",
    course_duration: "7 месяцев",
    completed: true,
  },
  {
    title: "Инженер по тестированию",
    description:
      "Описание: Вы научитесь находить ошибки в работе сайтов и приложений с помощью Java, JavaScript или Python.",
    course_duration: "7 месяцев",
    completed: true,
  },
  {
    title: 5,
    description: "123",
    course_duration: "da da da",
    completed: false,
  },
  {
    title: 6,
    description: "123",
    course_duration: "da da da",
    completed: false,
  },
  {
    title: 7,
    description: "123",
    course_duration: "da da da",
    completed: false,
  },
  {
    title: 8,
    description: "123",
    course_duration: "da da da",
    completed: false,
  },
  {
    title: 9,
    description: "123",
    course_duration: "da da da",
    completed: false,
  },
]);
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
