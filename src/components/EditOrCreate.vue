<template>
  <div>
    <FormCreate
      @set-card="addCard"
      :card-open-create="cardOpenCreate"
      @close-create-model="closeCreateModal"
    >
    </FormCreate>
    <FormEdit
      :card="cardForEdit"
      :card-modal-is-open="cardModalIsOpen"
      @set-card="updateCard"
      @save-card="saveCard"
      @open-modal="openModal"
      @close-modal="closeModal"
      @delete-modal="deleteModal"
      style="margin-top: 25px"
    ></FormEdit>
  </div>
</template>

<script setup>
import FormCreate from "./FormCreate.vue";
import FormEdit from "./FormEdit.vue";

import { ref } from "vue";
const props = defineProps({
  newCard: {
    type: Object,
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
]);
const newCard = ref({});

const closeCreateModal = () => {
  emit("close-create-model");
};

const addCard = (card) => {
  emit("set-card", card);
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

const deleteModal = () => {
  emit("delete-modal");
};
</script>
