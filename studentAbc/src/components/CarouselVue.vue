<template>
  <div class="carousel-container">
    <swiper :options="swiperOptions">
      <swiper-slide v-for="(item,index) in props.data" :key="index">
        <img :src="item" class="carousel-img" alt="">
        </swiper-slide>
      <div class="swiper-pagination"></div>
    </swiper>
  </div>
</template>

<script setup>
import { Swiper, SwiperSlide } from 'vue-awesome-swiper';
import {ref,onMounted} from 'vue';

const props = defineProps({
  data: Array
});
const swiperOptions = ref({
  pagination: {
    el: '.swiper-pagination',
    clickable: true
  },
  loop:true,//循环播放
  autoplay: {
    delay: 3000,//切换时间
    disableOnInteraction: false
  }

});
onMounted(()=>{
  console.log(props.data);
});
</script>

<style scoped>
.carousel-container {
  width: 100%;
  height: 100%;
  overflow: hidden;
}
.carousel-img{
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>