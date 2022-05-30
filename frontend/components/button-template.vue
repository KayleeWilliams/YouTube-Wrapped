<template> 
    <button @click="$emit('hideSection', buttonSection)" class="bg-violet-700 hover:bg-violet-500 select-none text-lg px-6 py-4 rounded-lg drop-shadow-lg transistion duration-500 ease-in-out"> {{ buttonText }} </button>
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
