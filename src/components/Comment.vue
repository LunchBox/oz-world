<script setup>
  const props = defineProps({
    comment: Object
  })
</script>

<template>
	<div class="comment">
		<div>
			<i class="fa-solid fa-user"></i>
      <b>{{ comment.user }}: </b>
      <span class="text">{{ comment.content }}</span>
		</div>

		<div class="status">
			<i class="fa-solid fa-heart"></i>
			1024

			<div style="margin-left: auto;">
				40個回應
				10次分享
			</div>
		</div>
		<div class="comment-actions">
      <a href="">
        <i class="fa-regular fa-thumbs-up"></i>
        讚好
      </a>
      <a href="">
        <i class="fa-regular fa-message"></i>
        回應
      </a>
      <a href="">
        <i class="fa-solid fa-share"></i>
        分享
      </a>
		</div>
	</div>
</template>

<style scoped>

b {
  font-weight: bold;
}

.comment {
	border: 1px solid #ccc;
	border-radius: 2px;
  padding: 10px;
}

.text {
}

.status {
	display: flex;
	align-items: center;
}

.comment-actions {
  display: flex;
  border-top: 1px solid #eee;
  padding-top: 10px;
  margin-top: 10px;
}
.comment-actions * {
  flex: 1;
  text-align: center;
}

</style>
