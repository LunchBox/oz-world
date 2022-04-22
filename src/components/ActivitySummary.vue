<script setup>
  import { ref } from "vue";
  const props = defineProps({
    activity: Object,
    mode: String
  });

  
  const selected = ref(false)
</script>

<template>
  <div @click="selected = !selected">
    <div class="activity">
      <div class="header">
        <h2>{{ activity.title }}</h2>
        <a href="" class="btn" style="margin-left: auto; ">
          <i class="fa-solid fa-check"></i>
          打卡
        </a>
      </div>

      <div class="meta tags">
        <i class="fa-solid fa-tag"></i>
        {{ activity.tag }}
      </div>

      <div class="meta addr">
        <i class="fa-solid fa-calendar"></i>
        {{ activity.date }} &middot;
        <i class="fa-solid fa-location-dot"></i>
        {{ activity.address }}
      </div>

      <div>
        {{ activity.desc }}
      </div>

      <div class="status">
        <i class="fa-solid fa-heart"></i>
        {{ Math.round(Math.random() * 1000) }}

        <div style="margin-left: auto;">
          {{ Math.round(Math.random() * 10) }}條路線
          {{ Math.round(Math.random() * 10) }}次分享
        </div>
      </div>
    </div>
    <div v-if="mode == 'guide' || selected" class="actions">
      <a href="">
        <i class="fa-regular fa-heart"></i>
        想去
      </a>
      <a href="">
        <i class="fa-regular fa-message"></i>
        留言
      </a>
      <a href="">
        <i class="fa-solid fa-share"></i>
        分享
      </a>
    </div>
  </div>
</template>

<style scoped>
	.activity {
    border: 2px solid;
		padding: 0.5em;


		position: relative;
	} 

	.header {
		display: flex;
		align-items: baseline;
	}

  .status {
    display: flex;
    align-items: center;
  }
  .status [data-icon] {
    margin-right: 4px;
  }

  h2 {
    font-weight: bold;
    margin-bottom: 0.5em;
  }

	.meta.addr {
		margin-bottom: 0.5em;
	}

  .actions {
    display: flex;
    padding: 10px;
  }
  .actions * {
    flex: 1;
    text-align: center;
  }

  .btn {
    border: 2px solid;
    padding: 10px;
    border-radius: 8px;
  }
</style>
