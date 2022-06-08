<template> 
    <button @click="$emit('hideSection', buttonSection)" class="bg-violet-700 hover:bg-violet-500 select-none text-lg px-6 py-4 rounded-lg drop-shadow-lg transition ease-in-out delay-150 duration-150 hover:-translate-y-1 hover:scale-105"> {{ buttonText }} </button>
</template>

<script setup lang="ts">
    // Props 
    interface Props {
        buttonSection: string
        buttonText: string
    }

    // Emits
    const emit = defineEmits(['hideSection'])

    const buttonProps = defineProps<Props>()
</script>
