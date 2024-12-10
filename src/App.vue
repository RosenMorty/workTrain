<template>
  <div class="container">
    <FormCreate />
    <WishList :cards="cards" />
  </div>
</template>

<script setup>
import { ref } from "vue";
import WishList from "./components/WishList.vue";
import FormCreate from "./components/FormCreate.vue";
import "./assets/global.css";

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
.spisok {
  text-align: center;
}
</style>
