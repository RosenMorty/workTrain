<template>
  <div>
    <div class="modal" v-if="cardOpenCreate">
      <div>
        <div class="modal-content">
          <div class="hedEdit">
            <h2>Форма создания {{ newCard.title }}</h2>
            <button
              class="closeBtn"
              style="background-color: white"
              type="button"
              @click="closeCreateModal"
            ></button>
          </div>
          <form @submit.prevent="addCard" class="form">
            <label>
              <span>Названине:</span>
              <input type="text" v-model="newCard.title" />
            </label>
            <label>
              <span>Описание:</span>
              <input type="text" v-model="newCard.description" />
            </label>
            <label>
              <span>Длительность:</span>
              <input type="text" v-model="newCard.course_duration" />
            </label>
            <button type="submit">Добавить</button>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const props = defineProps({
  newCard: {
    type: Object,
  },
  cardOpenCreate: {
    type: Boolean,
  },
});

const emit = defineEmits(["set-card", "card-open-create"]);
const newCard = ref({
  id: 0,
  title: "",
  description: "",
  course_duration: "",
  completed: true,
});

const closeCreateModal = () => {
  emit("close-create-model");
};

const addCard = () => {
  emit("set-card", {
    title: newCard.value.title,
    description: newCard.value.description,
    course_duration: newCard.value.course_duration,
    completed: newCard.value.completed,
  });
};
</script>

<style>
.hedEdit {
  display: flex;
  justify-content: space-between;
}
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
