<template>
  <div>
    <FormCreate
      v-if="cardOpenCreate"
      :card="card"
      :card-open-create="cardOpenCreate"
      @set-card="setCard"
      @add-card="addCard"
      @close-create-modal="closeCreateModal"
    >
    </FormCreate>
    <FormEdit
      v-if="cardModalIsOpen"
      :card="card"
      :card-modal-is-open="cardModalIsOpen"
      style="margin-top: 25px"
      @set-card="updateCard"
      @save-card="saveCard"
      @delete-modal="deleteModal"
      @close-modal="closeModal"
    ></FormEdit>
  </div>
</template>

<script setup>
import FormCreate from "./FormCreate.vue";
import FormEdit from "./FormEdit.vue";

import { ref } from "vue";
const props = defineProps({
  card: {
    type: Object,
    default: {},
  },
  cardOpenCreate: {
    type: Boolean,
  },
  cardModalIsOpen: {
    type: Boolean,
  },
});

const emit = defineEmits([
  "set-card",
  "card-open-create",
  "open-modal",
  "save-card",
  "close-modal",
  "delete-modal",
  "close-create-modal",
  "add-card",
]);

const setCard = (card) => {
  emit("set-card", card);
};

const closeCreateModal = () => {
  emit("close-create-modal");
};

const addCard = (card) => {
  emit("add-card", card);
};

const openModal = (card) => {
  emit("open-modal", card);
};

const saveCard = () => {
  emit("save-card");
};

const closeModal = () => {
  emit("close-modal");
};

const updateCard = (card) => {
  emit("set-card", card);
};

const deleteModal = () => {
  emit("delete-modal");
};
</script>
