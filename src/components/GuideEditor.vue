<script setup>

import { ref, computed } from "vue";

import GuideMap from "./GuideMap.vue";
import GuideSummary from "./GuideSummary.vue";
import GuideItem from "./GuideItem.vue";
import ItemEditor from "./ItemEditor.vue";

const e1 = {
  title: "DFS第十屆「傳世佳釀」",
  tag: "其他",
  date: "1-26/4",
  address: " DFS旗下澳門T廣場新濠天地店",
  location: {x: 55, y: 63},
  desc: "首次登陸澳門的「傳世佳釀」搜羅來自250多位收藏家及65個世界知名品牌的葡萄酒、烈酒及香檳，為品酒愛好者獨家呈獻過百款珍貴佳釀..."
}

const e2 = {
  title: "「POP INFINITY」 藝術展覽",
  tag: "展覽",
  date: "1-30/4",
  address: "摩珀斯酒店大堂",
  location: {x: 53, y: 61},
  desc: "展出以迪士尼經典角色為創作靈感的系列式藝術裝置，包括五件1.2米高的Snow Angel Mickey雕塑和多個藝術家的限量作品。WF Fashion旗艦店..."
}

const e3 = {
  title: "「Olá 土生菜」成果展示工作坊",
  tag: "工作坊",
  date: "30/4",
  address: "葡角餐廳",
  location: {x: 34, y: 19},
  desc: "澳門土生菜廚師向精神康復者學員教授土生葡人美食烹飪技藝，學員於成果展示日向公眾現場示範調製土生菜特色飲品，並奉上預先烹飪完成的土生菜..."
}

const es = [e1, e2, e3];

const c1 = {
  user: "Daniel Cheang",
  content: "首次登陸澳門的「傳世佳釀」搜羅來自250多位收藏家及65個世界知名品牌的葡萄酒、烈酒及香檳，為品酒愛好者獨家呈獻過百款珍貴佳釀..."
}

const i1 = {
  activity: e1,
  comment: c1
}


const i2 = {
  activity: e2
}

const i3 = {
  activity: e3,
}

const gl = {
  title: "文化傳播月 2022",
  user: "Daniel Cheang",
  desc: "今年「文化傳播月」帶來六大項目多角度的藝文體驗，包括以美學分享會、藝文工作坊、藝文空間、文化職業的精神等為主題的活動，豐富觀眾對文化和生活的感知，一同把文化的美好帶到四月日常。",
  items: [i1, i2, i3],
}


const mode = ref("view");

const selected = ref(0);

</script>

<template>
  <div class="container">
    <aside>
      <GuideMap :items="es" :selected="selected"/>
    </aside>
    <main style="display: flex; flex-direction: column;">
      <div class="guide-actions">
        <div v-if="mode == 'view'">
          <a href="" @click.prevent="mode = 'edit'">
            <i class="fa-solid fa-pencil"></i>
            編輯行程
          </a>
          <a href="" @click.prevent="mode = 'guide'">
            <i class="fa-solid fa-shoe-prints"></i>
            現在出發
          </a>
          <a href="" @click.prevent>
            <i class="fa-solid fa-plus"></i>
            創建新的路線
          </a>
        </div>
        <div v-if="mode != 'view'">
          <a href="" @click.prevent="mode = 'view'">
            <i class="fa-solid fa-check"></i>
            完成
          </a>
        </div>
      </div>

      <div style="flex: 1; padding: 10px; overflow-y: scroll;">
        <GuideSummary :guide="gl" />
        <GuideItem 
          v-for="(item, idx) in gl.items" 
          :item="item" 
          :index="idx" 
          :selected="idx === selected"
          :mode="mode"
          @click="selected = idx"
          />

        <ItemEditor v-if="mode == 'edit'" />
      </div>
    </main>
  </div>
</template>

<style>
  * {
    font-family: Noto Sans, Helvetica Neue, Helvetica, Arial, Microsoft JhengHei,
    MingLiU_HKSCS-ExtB, PMingLiU, PingFang HK, Apple LiGothic Medium,
    LiHei Pro Medium, WenQuanYi Micro Hei, sans-serif;

    font-weight: bold;
    color: #000;
  }

  .container {
    line-height: 1.5em;
    border: 2px solid;
    position: relative;
    width: 100%;
    height: 100%;

    display: flex;
    color: #69797e;
    color: #000;

    font-size: 16px;
    line-height: 1.63;

    box-sizing: content-box;
  }

  img {
    max-height: 100%;
  }
</style>

<style scoped>
  .guide-actions {
    background: #efefef;
    padding: 10px;
  }

  .guide-actions a {
    color: #333;
    text-decoration: none;
    margin: 0 0.5em;
  }
</style>
