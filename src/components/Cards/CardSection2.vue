<template>
    <div class="card-content">
        <h2 class="title">{{ title }}</h2>
        <p class="percentage">{{ percentage }}</p>
        <p class="description">{{ description }}</p>
    </div>
</template>

<script setup>
const props = defineProps({
    title: {
        type: String,
        required: true,
    },
    percentage: {
        type: String,
        required: true,
    },
    description: {
        type: String,
        required: true,
    },
});
</script>

<style scoped>
.card-content {
    /* background-color: #f0f0f0; */
    padding: 20px;
    text-align: center;
    border-radius: 8px;
    /* box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); */
    font-family: Montserrat, sans-serif;
    /* display: flex; */
    /* flex-direction: column; */
    /* justify-content: space-between; */
    /* height: 100%; */
}
</style>