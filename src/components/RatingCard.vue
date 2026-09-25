<script setup lang="ts">
import { ref } from 'vue';

const emit = defineEmits<{
    submit: [number]
}>()

const ratings = [1, 2, 3, 4, 5];
const selectedRating = ref(0);
function handleSubmit() {
    if (selectedRating.value === 0) return;
    emit('submit', selectedRating.value);
}

</script>

<template>
    <div class="star-icon">
        <img src="../assets/icon-star.svg" alt="">
    </div>

    <h1>How did we do?</h1>

    <p>
        Please let us know how we did with your support request.
        All feedback is appreciated to help us improve our offering!
    </p>

    <div class="note-button__list">
        <button v-for="rating in ratings" :key="rating" class="note-button"
            :class="{ selected: rating === selectedRating }" type="button" @click="selectedRating = rating">
            {{ rating }}
        </button>
    </div>

    <button class="submit-button" type="button" :disabled="selectedRating === 0" @click="handleSubmit">
        Submit
    </button>
</template>

<style scoped>
.star-icon {
    width: 36px;
    height: 36px;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: var(--color-gray-900);
    border-radius: 50%;
}


h1 {
    color: var(--color-white)
}

p {
    color: var(--color-gray-500);
}

.note-button__list {
    display: flex;
    justify-content: space-between;
}

.note-button {
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--color-gray-500);
    background-color: var(--color-gray-900);
    font-weight: 700;
    padding: 20px;
    border-radius: 50%;
    border: none;
    width: 2.25rem;
    height: 2.25rem;
    cursor: pointer;

    &:hover {
        background-color: var(--color-white);
        color: var(--color-gray-900);
    }

}

.selected {
    background-color: var(--color-orange);
    color: var(--color-gray-900);
}

.submit-button {
    color: var(--color-gray-900);
    background-color: var(--color-orange);
    padding: 10px;
    border-radius: 20px;
    border: none;
    cursor: pointer;
    text-transform: uppercase;
    letter-spacing: 2px;
    text-align: center;
    font-weight: 700;

    &:hover {
        background-color: var(--color-white);
    }

    &:disabled {
        opacity: 0.5;
        cursor: not-allowed;
    }
}
</style>