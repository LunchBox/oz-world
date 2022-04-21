<script setup>
  const props = defineProps({
    items: Array
  })
</script>

<template>
  <div class="map">
    <img src="https://upload.wikimedia.org/wikipedia/commons/0/01/China_Macau_location_map.svg" alt="map">

    <div class="toolbar">
      <button>
        <i class="fa-solid fa-plus"></i>
      </button>
      <button>
        <i class="fa-solid fa-minus"></i>
      </button>

      <button>
        <i class="fa-solid fa-caret-up"></i>
      </button>
      <button>
        <i class="fa-solid fa-caret-down"></i>
      </button>

      <button>
        <i class="fa-solid fa-hand-back-fist"></i>
      </button>

      <button>
        <i class="fa-solid fa-location-crosshairs"></i>
      </button>
    </div>


    <div v-for="(e, idx) in items" :key="idx" class="dot" :style="{left: e.location.x + 'px', top: e.location.y + 'px'}">{{ idx + 1}}</div>
  </div>
</template>

<style scoped>
img {
  display: block;
}

.toolbar {
  position: absolute;
  right: 0.5em;
  top: 0.5em;
}

.toolbar button {
  border: 1px solid #ccc;
  background: #fff;

  color: #ccc;
  width: 24px;
  height: 24px;
  display: flex;
  padding: 0;
  margin: 0;
  align-items: center;
  justify-content: center;
  font-size: 12px;
}

.toolbar button [data-icon] {
  margin: 0;
}



.dot {
  position: absolute;
  width: 18px;
  height: 18px;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 2px solid #ccc;
  border-radius: 50%;
  background: #fff;
  font-size: 12px;

  color: #ccc;
}

.dot.active {
  border-color: orange;
  background: orange;
  color: #fff;
}
</style>
