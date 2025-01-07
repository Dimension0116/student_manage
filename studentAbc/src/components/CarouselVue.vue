<template>
    <!-- 
    slides-per-view: 每次显示的slide数量
    space-between: slide之间的间距
    swiper:这个属性是一个事件监听器，当 Swiper 初始化完成时会触发名为 "onSwiper" 的方法。
    slideChange:这个属性是一个事件监听器，当 Swiper 切换到另一个 slide 时会触发名为 "onSlideChange" 的方法。
    pagination: 分页器
    autoplay: 自动播放
    loop: 循环播放
    navigation: 导航按钮
    -->
    
    <swiper
        class="swiper-container"
        :slides-per-view="1"
        :space-between="0"
        @swiper="onSwiper"
        @slideChange="onSlideChange"
        :modules="modules"
        :pagination="{ clickable: true }"
        :autoplay="{ delay: 2500, disableOnInteraction: false }"
        :loop="true"

    >
        <swiper-slide v-for="(item,index) in props.imgPaths" :key="index">
            <img :src="item" :alt="index" class="item"/>
        </swiper-slide>
        
    </swiper>

</template>

<script setup>
//导入swiper组件
import { Swiper, SwiperSlide } from 'swiper/vue';
//导入swiper module
import {Navigation,Pagination,A11y,Autoplay} from 'swiper/modules';
//导入相关样式
import 'swiper/swiper-bundle.css';
import {ref,onMounted,onBeforeUnmount} from 'vue';
const modules = [Navigation,Pagination,A11y,Autoplay];
const onSwiper = (swiper) => console.log(swiper);
const onSlideChange = () => console.log('slide change');
const props= defineProps( {
    imgPaths:Array
});
</script>

<style scoped>
.swiper-container {
  flex:1;
  background-color: white;
  border-radius: 4px;
  width: 100px;
  height: 200px;
}

.item {
  width: 100%;
  border-radius: 4px;
  height: 100%;
  object-fit: cover;
}
</style>