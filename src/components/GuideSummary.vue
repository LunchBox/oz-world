<script setup>
  const props = defineProps({
    guide: Object
  })
</script>

<template>
  <div>
    <h1>{{ guide.title }}</h1>
		<div class="actions">
      <a href="">
        <i class="fa-solid fa-user"></i>
        {{ guide.user }}
      </a>
      <a href="">
        <i class="fa-solid fa-thumbs-up"></i>
        讚好
      </a>
      <a href="">
        <i class="fa-solid fa-bookmark"></i>
        收藏
      </a>
      <a href="">
        <i class="fa-solid fa-share"></i>
        分享
      </a>
		</div>
    <p>{{ guide.desc }} </p>

  </div>
</template>

<style scoped>
  h1 {
    font-size: 18px;
    font-weight: bold;
    margin: 1em 0;
  }

  .actions {
    display: flex;
    margin: 0.5em 0;
    font-size: smaller;
  }
  .actions > * {
    margin-right: 1em;
  }
</style>
