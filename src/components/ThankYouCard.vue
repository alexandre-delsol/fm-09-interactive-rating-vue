<script setup lang="ts">
defineProps<{
    selectedRating: number;
}>()
</script>

<template>
  <img src="../assets/illustration-thank-you.svg" alt="">
    <p>You selected {{ selectedRating }} out of 5</p>
    <h1>Thank you!</h1>
    <p>We appreciate you taking the time to give a rating. If you ever need more support,
      don’t hesitate to get in touch!</p>
</template>

<style scoped>
h1 {
    color: var(--color-white)
}

p {
    color: var(--color-gray-500);
}
</style>