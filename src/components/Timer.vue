<script setup lang="ts">
    defineProps<{ count: string, label: string}>();
</script>

<template>
    <div class="wrapper">
        <div class="count">{{ count }}</div>
        <div class="label">{{ label }}</div>
    </div>
</template>

<style scoped>
.count {
    font-size: 4rem;
    font-weight: 800;
    
}
</style>