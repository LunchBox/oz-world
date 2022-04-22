<script setup>
  const props = defineProps({
    items: Array,
    selected: Number,
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

      &nbsp;

      <button>
        <i class="fa-solid fa-location-crosshairs"></i>
      </button>
    </div>


    <div 
      v-for="(e, idx) in items" 
      :key="idx" 
      class="dot" 
      :class="{active: idx == selected}" 
      :style="{left: e.location.x + '%', top: e.location.y + '%'}">
      {{ idx + 1}}
    </div>
  </div>
</template>

<style scoped>

.map {
  height: 100%;
}

img {
  display: block;
  height: 100%;
}

.toolbar {
  position: absolute;
  right: 0.5em;
  top: 0.5em;
}

.toolbar button {
  border: 2px solid;
  background: #fff;

  width: 24px;
  height: 24px;
  display: flex;
  padding: 0;
  margin: 0;
  align-items: center;
  justify-content: center;
  font-size: 12px;

  margin-bottom: 1px;
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
  border: 2px solid;
  border-radius: 50%;
  background: #fff;
  font-size: 12px;

  transform: translate(-50%, -50%);
}

.dot.active {
  border-color: orange;
  background: orange;
  color: #fff;

  width: 24px;
  height: 24px;
  z-index: 10;
}
</style>
