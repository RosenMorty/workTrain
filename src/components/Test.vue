<template>
  <div class="body_card">
    <div class="card" v-for="item in cards" :key="item.id">
      <!-- <div class="card-title">{{ item.title }}</div>
      <div class="card-description">{{ item.description }}</div>
      <div class="card-course_duration">{{ item.course_duration }}</div>
      <div class="card-completed"> -->
      <div v-if="item.completed" :class="card - is - completed">
        <div class="card-title">{{ item.title }}</div>
        <div class="card-description">{{ item.description }}</div>
        <div class="card-course_duration">{{ item.course_duration }}</div>
        <div class="card-completed"></div>
      </div>
      <div v-else class="card-is-not-completed">
        Кажется, курс уже не существует…
      </div>
    </div>
  </div>
  <!-- </div> -->
</template>

<script setup>
import { ref } from "vue";

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

<style>
.card {
  width: 300px;
  padding: 24px 24px 16px;
  background-color: #f0ebeb;
  border-radius: 16px;
  margin-bottom: 16px;
  margin-right: 16px;
}

.body_card {
  display: flex;
  align-items: center;
  width: 750px;
  height: 750px;
  flex-direction: row;
  flex-wrap: wrap;
  margin-left: 500px;
}

.card-title {
  font-size: 18px;
  font-weight: 600;
  margin-bottom: 8px;
}

.card-description {
  color: rgb(106, 109, 114);
  margin-bottom: 16px;
}

.card-completed {
  margin-top: 5px;
  display: flex;
  align-items: center;
  gap: 4px;
}

.card-is-completed {
  padding: 0 6px;
  border: 1px solid rgb(42, 182, 231);
  color: rgb(42, 182, 231);
  border-radius: 4px;
}

.card-is-not-completed {
  padding: 0 6px;
  /* border: 1px solid rgb(220, 115, 189); */
  color: rgb(220, 115, 189);
  border-radius: 4px;
}

.form {
  margin-bottom: 12px;
}

input {
  margin-left: 4px;
  margin-bottom: 8px;
}
</style>
