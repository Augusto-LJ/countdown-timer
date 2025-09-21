<script setup lang="ts">
    defineProps<{ label: string}>();
</script>

<template>
    <div class="wrapper">
        <div class="count">12</div>
        <div class="label">{{ label }}</div>
    </div>
</template>

<style scoped>
.count {
    font-size: 4rem;
    font-weight: 800;
    
}
</style>