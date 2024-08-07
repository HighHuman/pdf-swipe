<template>
  <div class="wrap">
    <swiper
      class="mySwiper"
      :pagination="{ clickable: true }"
      :slides-per-view="1"
    >
      <swiper-slide v-for="(page, index) in imgArr" :key="index">
        <img :src="page" alt="" />
      </swiper-slide>
    </swiper>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";

const imgArr = ref<string[]>([]);

onMounted(() => {
  for (let i = 1; i < 106; i++) {
    imgArr.value.push(
      "/public/1723037447473-b7a58447-d809-4548-a487-120e19583bab_" + i + ".jpg"
    );
  }
});
</script>

<style scoped>
.wrap {
  height: 100vh;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  box-sizing: content-box;
  overflow: hidden;
}
/* .mySwiper {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: row;
} */

img {
  object-fit: cover;
  max-height: 98vh;
  max-width: 98vw;
}
.swiper-slide {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: row;
}
</style>
