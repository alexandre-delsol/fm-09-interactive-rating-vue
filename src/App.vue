<script setup lang="ts">
import RatingCard from './components/RatingCard.vue';
import ThankYouCard from './components/ThankYouCard.vue';
import { ref } from "vue";

const submit = ref(false);
const selectedRating = ref(0);

</script>

<template>
  <main>
    <Transition name="card">

      <RatingCard v-if="!submit" @submit="(rating) => {
        selectedRating = rating;
        submit = true;
      }" />

      <ThankYouCard v-else :selectedRating />

    </Transition>
  </main>
</template>

<style scoped>
main {
  background: HSL(213, 19%, 18%);
  background: linear-gradient(180deg, rgba(37, 45, 55, 1) 0%, rgba(18, 15, 20, 1) 100%);
  border-radius: 20px;
  padding: 30px;
  gap: 20px;
  width: 80%;
  max-width: 400px;
  display: flex;
  flex-direction: column;
}

.card-enter-active,
.card-leave-active {
  transition: opacity 0.3s ease, transform 0.3s ease;
}

.card-enter-from {
  opacity: 0;
  transform: translateY(10px);
}

.card-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
