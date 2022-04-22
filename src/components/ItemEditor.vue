<script setup>
import ActivitySummary from "./ActivitySummary.vue";

const e1 = {
  title: "2022 年春季塔石藝墟",
  tag: "節日盛事",
  date: "21-24/4",
  address: "塔石廣場",
  location: {x: 280, y: 510},
  desc: "本地著名文創市集「塔石藝墟」舉辦至今已踏入第14年，每年分為春季和秋季兩期。今年春季塔石藝墟由每周舉辦3日增至4日..."
}
</script>

<template>
  <div class="editor">
    <h2>新增遊覽節目</h2>
    <form action="">
      <div class="input-field">
        <label for="">地點或活動</label>
        <ActivitySummary :activity="e1" />
      </div>
      <div class="input-field">
        <label for="">介紹</label>
        <textarea>藝墟的市集包羅萬有，甚麼的奇貨你都能在這裡挖到</textarea>
      </div>
      <div class="input-field">
        <label for="">預計需時</label>
        <input type="number" value=1.0 step=0.5> hours
      </div>

      <div>
        <button>
          提交
        </button>
      </div>
    </form>
  </div>
</template>

<style scoped>

.editor {
  border: 2px solid;
  padding: 10px;

  margin-bottom: 6em;
}

.input-field {
  margin-bottom: 1em;
}

h2 {
  font-weight: bold;
  margin-bottom: 0.5em;
}

label {
  display: block;
}

textarea{
	width: 100%;
	height: 6em;
	border: 2px solid;
	border-radius: 2px;

	box-sizing: border-box;

	font-size: 16px;
}

input {
	border: 2px solid;
	border-radius: 2px;

  font-size: 16px;
}

button {
	border: 2px solid;
	border-radius: 2px;
  background: #fff;

  font-size: 16px;
  
}
</style>
