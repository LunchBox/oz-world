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
      <ActivitySummary :activity="item.activity" v-if="selected" :mode="mode"/>
      <div v-else class="item-header">
        <h2>{{ item.activity.title }}</h2>
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
  padding: 0.5em;
  border: 2px solid;

  display: flex;

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
	width: 36px;
  height: 36px;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 2px solid;
  border-radius: 50%;
  background: #fff;

}

.item.active .dot {
  border-color: orange;
  background: orange;
  color: #fff;

  font-size: 18px;

  margin-top: 0.5em;
}


</style>
