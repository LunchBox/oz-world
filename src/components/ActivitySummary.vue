<script setup>
  const props = defineProps({
    activity: Object
  })
</script>

<template>
	<div class="activity">
		<div class="header">
      <h2>{{ activity.title }}</h2>
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
				40條路線
				10次分享
			</div>
		</div>
	</div>
</template>

<style scoped>
	.activity {
		border: 1px solid #ccc;
		border-radius: 2px;
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
</style>
