<template>
  <div v-if="card.completed" class="card-is-completed">
    <div class="card-title">{{ card.title }}</div>
    <div class="card-description">{{ card.description }}</div>
    <div class="card-course_duration">{{ card.course_duration }}</div>
    <div class="card-completed"></div>
  </div>
  <div v-else class="card-is-not-completed">
    Кажется, курс уже не существует…
  </div>
</template>

<script setup>
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
  width: 300px;
  padding: 24px 24px 16px;
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
  padding: 0 6px;
  border: 1px solid rgb(42, 182, 231);
  color: rgb(42, 182, 231);
  border-radius: 4px;
}

.card-is-not-completed {
  padding: 0 6px;
  border: 1px solid rgb(166, 182, 197);
  color: rgb(166, 182, 197);
  border-radius: 4px;
}
</style>
