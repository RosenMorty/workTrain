<template>
  <div class="container">
    <FormCreate 
    @set-card="addCard"
    ></FormCreate>
    <FormEdit
      :card="cardForEdit"
      @set-card="updateCard"
      :card-modal-is-open="cardModalIsOpen"
      @save-card="saveCard"
      @open-modal="openModal"
      @close-modal="closeModal"
      @delete-modal="deleteModal"
      style="margin-top: 25px"
    />
    <WishList
      v-if="!cardsIsLoading"
      :cards="cards"
      @click-by-card="openCardForEdit"
    />
    <img v-else src="/loading.gif" alt="loading" />
  </div>
</template>

<script setup>
import { ref } from "vue";
import WishList from "./components/WishList.vue";
import "./assets/global.css";
import FormEdit from "./components/FormEdit.vue";
import FormCreate from "./components/FormCreate.vue";

const cardModalIsOpen = ref(false);

const cards = ref([]);

const cardsIsLoading = ref(false);

const loadCards = () => {
  cardsIsLoading.value = true;
  setTimeout(() => {
    cards.value = [
      {
        id: 1,
        title: "Python-разработчик",
        description:
          "Описание: На Python пишкт сайты, приложения, игры и чат-боты. Netflix, Spotify, Google и Youtube написаны на Python.",
        course_duration: "10 месяцев",
        completed: true,
      },
      {
        id: 2,
        title: "Графический дизайнер",
        description:
          "Описание: Научим делать бренды узнаваемымми через создание логотипов, графики для рекламы, упаковки и не только.",
        course_duration: "6 месяцев",
        completed: true,
      },
      {
        id: 3,
        title: "Веб-разработчик",
        description:
          "Описание: Веб-разработчик создает сайты, сервисы и приложения, которыми мы ежедневно пользуемся.",
        course_duration: "7 месяцев",
        completed: true,
      },
      {
        id: 4,
        title: "Инженер по тестированию",
        description:
          "Описание: Вы научитесь находить ошибки в работе сайтов и приложений с помощью Java, JavaScript или Python.",
        course_duration: "7 месяцев",
        completed: true,
      },
      {
        id: 5,
        title: 5,
        description: "123",
        course_duration: "da da da",
        completed: false,
      },
      {
        id: 6,
        title: 6,
        description: "123",
        course_duration: "da da da",
        completed: false,
      },
      {
        id: 7,
        title: 7,
        description: "123",
        course_duration: "da da da",
        completed: false,
      },
      {
        id: 8,
        title: 8,
        description: "123",
        course_duration: "da da da",
        completed: false,
      },
      {
        id: 9,
        title: 9,
        description: "123",
        course_duration: "da da da",
        completed: false,
      },
    ];
    cardsIsLoading.value = false;
  }, 2000);
};

loadCards();

const cardForEdit = ref({
  id: 0,
  title: "",
  description: "",
  course_duration: "",
  completed: false,
});

const saveCard = () => {
  const newCard = Object.assign({}, cardForEdit.value);
  cards.value = cards.value.map((el) => (el.id === newCard.id ? newCard : el));
  closeModal();
};

const deleteModal = (card) => {
  const newCard = Object.assign({}, cardForEdit.value);
  cards.value = cards.value.filter((card) => card.id !== newCard.id)
  closeModal();
}

const updateCard = (card) => {
  cardForEdit.value = card;
};

const openCardForEdit = (card) => {
  openModal();
  cardForEdit.value = Object.assign({}, card);
};

const addCard = (card) => {
  cards.value.unshift(card)
}

const openModal = () => {
  cardModalIsOpen.value = true;
};
const closeModal = () => {
  cardModalIsOpen.value = false;
  cardForEdit.value = {
    id: 0,
    title: "",
    description: "",
    course_duration: "",
    completed: false,
  };
};
</script>

<style scoped>
.spisok {
  text-align: center;
}
</style>
