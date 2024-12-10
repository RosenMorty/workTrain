<template>
  <div>
    <button @click="openModal">Форма редактирования</button>

    <div class="modal" v-if="isModalOpen">
      <div class="modal-content">
        <h2>Форма редактирование</h2>
        <form @submit.prevent="saveCard" class="form">
          <label>
            <span>Названине:</span>
            <input type="text" :value="card.title" @input="setTitle" />
          </label>
          <label>
            <span>Описание:</span>
            <input
              type="text"
              :value="card.description"
              @input="setDescription"
            />
          </label>
          <label>
            <span>Длительность:</span>
            <input
              type="text"
              :value="card.course_duration"
              @input="setCurseDuration"
            />
          </label>
          <button type="submit" style="margin-bottom: 10px">Сохранить</button>
          <button type="button" @click="closeModal">Закрыть</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const isModalOpen = ref(false);
const props = defineProps({
  card: {
    type: Object,
  },
});
const emit = defineEmits(["set-card", "save-card", "open-modal"]);

const setTitle = (event) => {
  const data = Object.assign({}, props.card);
  data.title = event.target.value;
  emit("set-card", data);
};
const setDescription = (event) => {
  const data = Object.assign({}, props.card);
  data.description = event.target.value;
  emit("set-card", data);
};

const setCurseDuration = (event) => {
  const data = Object.assign({}, props.card);
  data.course_duration = event.target.value;
  emit("set-card", data);
};

const saveCard = () => {
  emit("save-card");
};

const openModal = () => {
  isModalOpen.value = true;
};

const closeModal = () => {
  isModalOpen.value = false;
};
</script>

<style>
.modal {
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: 1000;
}

.modal-content {
  background-color: #fff;
  border-radius: 8px;
  padding: 20px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  width: 400px;
}

h2 {
  margin: 0 0 20px;
  font-size: 24px;
  color: #333;
}

.form {
  display: flex;
  flex-direction: column;
}

label {
  margin-bottom: 15px;
}

label span {
  display: block;
  margin-bottom: 5px;
  font-weight: bold;
  color: #666;
}

input[type="text"] {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 16px;
  color: #333;
}

input[type="text"]:focus {
  border-color: #007bff;
  outline: none;
}

button {
  padding: 10px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
}

button:hover {
  background-color: #0056b3;
}
</style>
