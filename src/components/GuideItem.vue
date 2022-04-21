<script setup>

  import { computed } from "vue";

  import ActivitySummary from "./ActivitySummary.vue";
  import Comment from "./Comment.vue";
  const props = defineProps({
    item: Object,
		index: Number,
		selected: Boolean,
    mode: String,
  });

  const editing = computed(() => props.mode === "edit");
  const guiding = computed(() => props.mode === "guide");

</script>

<template>
  <div class="item" :class="{active: selected}">
    <div class="item-aside">
      <div class="dot">
        {{ index + 1}}
      </div>
    </div>
    <div class="item-main">
      <ActivitySummary :activity="item.activity" v-if="selected"/>
      <div v-else class="item-header">
        <h2>{{ item.activity.title }}</h2>
      </div>

      <div v-if="selected && guiding" class="item-actions">
        <a href="">
          <i class="fa-solid fa-check"></i>
          打卡
        </a>
        <a href="">
          <i class="fa-solid fa-message"></i>
          回應
        </a>
        <a href="">
          <i class="fa-solid fa-share"></i>
          分享
        </a>
      </div>

      <div v-if="selected && item.comment" style="margin-top: 10px;">
        <Comment :comment="item.comment" />
      </div>
    </div>
    <div class="item-aside-actions">
      <a href="" v-if="editing">
        <i class="fa-solid fa-xmark"></i>
      </a>
    </div>
  </div>
</template>

<style scoped>
.item {
  margin: 10px 0;
  border: 1px solid #ccc;
  border-radius: 2px;
  padding: 0.5em;

  display: flex;
  align-items: baseline;

  position: relative;
}

.item.active {
  border-color: orange;
}

.item-aside {
	flex: 0 0 48px;
  display: flex;
	justify-content: center;
}

.item-aside-actions {
  padding-left: 10px;
}

.item-main {
	flex: 1;
}

.item-header {
	display: flex;
	align-items: center;
}
.item-header .fa-xmark {
	margin-left: auto;
}


.dot {
  width: 24px;
  height: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 2px solid #ccc;
  border-radius: 50%;
  background: #fff;
  font-size: 12px;

  color: #ccc;
}

.item.active .dot {
  border-color: orange;
  background: orange;
  color: #fff;

	width: 36px;
  height: 36px;
  font-size: 18px;
}

.item-actions {
  display: flex;
  padding: 10px;
}
.item-actions * {
  flex: 1;
  text-align: center;
}

</style>
