<script setup>
  const props = defineProps({
    guide: Object
  })
</script>

<template>
  <div>
    <h1>{{ guide.title }}</h1>
    <p>{{ guide.desc }} </p>
  </div>
</template>

<style scoped>
  h1 {
    font-size: 18px;
    font-weight: bold;
    margin: 1em 0;
  }
</style>
