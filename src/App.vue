<script setup lang="ts">
import RatingCard from './components/RatingCard.vue';
import ThankYouCard from './components/ThankYouCard.vue';
import { ref } from "vue";

const submit = ref(false);
const selectedRating = ref(0);

</script>

<template>
  <main>

    <RatingCard v-if="!submit" @submit="(rating) => {
      selectedRating = rating;
      submit = true;
    }" />

    <ThankYouCard v-else :selectedRating />

  </main>

</template>

<style scoped>
main {
  background-color: var(--color-gray-950);
  border-radius: 20px;
  padding: 30px;
  gap: 20px;
  width: 80%;
  max-width: 400px;
  display: flex;
  flex-direction: column;
}
</style>
