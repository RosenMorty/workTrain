<template>
  <div>
    <div class="modal">
      <div>
        <div class="modal-content">
          <div class="hedEdit">
            <h2>Форма создания {{ card.title }}</h2>
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
  card: {
    type: Object,
  },
  cardOpenCreate: {
    type: Boolean,
  },
});

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

const emit = defineEmits(["set-card", "close-create-modal", "add-card"]);

const closeCreateModal = () => {
  emit("close-create-modal");
};

const addCard = () => {
  emit("add-card", {
    title: props.card.title,
    description: props.card.description,
    course_duration: props.card.course_duration,
    completed: true,
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
