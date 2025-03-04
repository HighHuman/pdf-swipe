<template>
  <div class="wrap">
    <swiper
      class="mySwiper"
      :pagination="{ clickable: true, type: 'fraction' }"
      :slides-per-view="1"
    >
      <swiper-slide v-for="(page, index) in imgArr" :key="index">
        <img :src="page" :alt="`${index}`" />
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
  for (let i = 1; i < 413; i++) {
    imgArr.value.push(
      "/assets/1741097062991-648bf582-2380-43b3-b11e-e5f74c650ba1_" + i + ".jpg"
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
