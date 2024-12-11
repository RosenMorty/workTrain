<template>
  <div class="card">
    <div v-if="card.completed" class="card-is-completed">
      <div class="card-title">{{ card.title }}</div>
      <div class="card-description">{{ card.description }}</div>
      <div class="card-course_duration">{{ card.course_duration }}</div>
      <div class="card-completed"></div>
    </div>
    <div v-else class="card-is-not-completed">
      Кажется, курс уже не существует…
    </div>
  </div>
</template>

<script setup>
import FormEdit from "./FormEdit.vue";
const props = defineProps({
  index: {
    type: Number,
  },
  card: {
    type: Object,
  },
});
</script>

<style>
.card {
  cursor: pointer;
  width: 300px;
  background-color: #fff;
  border-radius: 16px;
  margin-bottom: 16px;
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
  display: flex;
  align-items: center;
  gap: 4px;
}

.card-is-completed {
  padding: 24px 24px 16px;
  border: 1px solid rgb(42, 182, 231);
  color: rgb(42, 182, 231);
  border-radius: 16px;
}

.card-is-not-completed {
  width: 300px;
  text-align: center;
  border: 1px solid rgb(166, 182, 197);
  color: #e1a0ad;
  border-radius: 16px;
}
</style>
