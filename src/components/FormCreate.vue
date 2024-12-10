<template>
  <h2>Форма создания {{ newCard.title }}</h2>
  <form @submit.prevent="addCard" class="form">
    <label>
      <span>Названине:</span>
      <input type="text" v-model="newCard.title" />
    </label>
    <label>
      <span>Описание:</span>
      <input type="text" v-model="newCard.description" />
    </label>
    <button type="submit">Добавить</button>
  </form>
</template>

<script setup>
import { ref } from "vue";
const newCard = ref({
  id: 0,
  title: "",
  description: "",
  course_duration: "",
  completed: false,
});

// const setTitle = (event) => {
//   const value = event.target.value;
//   newCard.title = value;
// };
// const setDescription = (event) => {
//   const value = event.target.value;
//   newCard.description = value;
// };

const addCard = () => {
  console.log(newCard);
};
</script>

<style>
.form {
  display: flex;
  flex-direction: column;
  margin-bottom: 12px;
}

input {
  margin-left: 4px;
  margin-bottom: 8px;
}

button {
  width: 180px;
}
</style>
