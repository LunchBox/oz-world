<script setup>
</script>

<template>
  <div class="container">
    <aside>
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

			<img src="https://upload.wikimedia.org/wikipedia/commons/0/01/China_Macau_location_map.svg" alt="map">

			<div class="dot" style="left: 170px; top: 125px;">3</div>
			<div class="dot" style="left: 270px; top: 495px;">2</div>
			<div class="dot active" style="left: 280px; top: 510px;">1</div>

			<div class="red-dot-wrapper">
				<div class="red-dot"></div>
				<div class="red-dot" style="margin: 12px 0 0 12px; zoom: 1.6;"></div>
				<div class="red-dot" style="margin: 18px 0 0 2px;zoom: 0.5"></div>
				<div class="red-dot" style="margin: 4px 0 0 6px; zoom: 0.8"></div>
				<div class="red-dot" style="margin: 8px 0 0 0px; zoom: 1.2"></div>
				<div class="red-dot" style="margin: 4px 0 0 12px;"></div>
			</div>
    </aside>
  </div>
</template>

<style>
  * {
    font-family: Noto Sans, Helvetica Neue, Helvetica, Arial, Microsoft JhengHei,
    MingLiU_HKSCS-ExtB, PMingLiU, PingFang HK, Apple LiGothic Medium,
    LiHei Pro Medium, WenQuanYi Micro Hei, sans-serif;
  }

  #container {
    line-height: 1.5em;
    border: 1px solid #333;
    position: relative;

    display: flex;
    color: #69797e;

    font-size: 15px;
  }
</style>
