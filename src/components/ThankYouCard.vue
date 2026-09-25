<script setup lang="ts">
defineProps<{
    selectedRating: number;
}>()
</script>

<template>
    <div class="thank-you-card">
        <img class="thank-you-image" src="../assets/illustration-thank-you.svg" alt="">

        <p class="rating-result">
            You selected {{ selectedRating }} out of 5
        </p>

        <h1>Thank you!</h1>

        <p class="description">
            We appreciate you taking the time to give a rating. If you ever need more support,
            don’t hesitate to get in touch!
        </p>
    </div>
</template>

<style scoped>

.thank-you-card{
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: 20px;
}

.rating-result {
    color: var(--color-orange);
    background-color: var(--color-gray-900);
    padding: 8px 16px;
    border-radius: 20px;
}

h1 {
    color: var(--color-white)
}

.description {
    color: var(--color-gray-500);
    font-size: 15px;
}
</style>