<template>
  <div class="text-9xl font-bold text-white flex flex-col gap-y-32 items-center text-center	">

    <p> YouTube <br> Wrapped </p>

    <button-template @hideSection="relay" buttonSection="title" buttonText="Get Started" />
  </div>
</template>

<script setup lang="ts">
  // Emits
  const emit = defineEmits(['hideSection'])

  // Functions
  function relay(section) {
    emit('hideSection', section)

  }
</script>
