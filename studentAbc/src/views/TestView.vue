<script setup>
import CardVue from '../components/Card.vue'
import LayoutLine from '../components/LayoutLine.vue'
import EchartsVue from '@/components/EchartsVue.vue';
import IconVue from '../components/IconVue.vue'
import CarouselVue from '@/components/CarouselVue.vue';
import { ref } from 'vue'
const imgPathCarsel = ref([
    '../src/assets/images/img1.jpg',
    '../src/assets/images/img2.jpg',
    '../src/assets/images/img3.jpg',
    '../src/assets/images/img4.jpg',
  ])
</script>
<template>
  <div class="root">
    <CarouselVue />
    
  </div>
</template>
<style scoped>
.root{
    display: flex;
    /* margin: 20px; */
    background-color: transparent;
    overflow: auto;
    /* background-color: aqua; */
    border-radius: 4px;
    height: 100%;
    width: 100%;
}
.root-left{
    display: flex;
    flex:3 0 0;
    /* background-color: #ffffff; */
    flex-direction: column;

}
.root-right{
    display: flex;
    flex-direction: column;
    flex:1 0 0;
    background-color: transparent;

}
.layout-line001{
    display: flex;
    flex:3 0 0;
    flex-direction: column;
    background-color: #ffffff;
    border-radius: 4px;
    padding: 20px;
}
.layout-line002{
    display: flex;
    flex:2 0 0;
    flex-direction: column;
    background-color: #ffffff;
}
.card-layout-line{
    display: flex;
    flex-direction: row;
    justify-content: left;
    border-top: 1px solid #F2F3F5;
    border-bottom: 1px solid #F2F3F5;
    flex-wrap: wrap;
}
.layout-line-spacebetween{
    display: flex;
    /* flex: 1 0 0; */
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    padding: 10px;
}
.layout-line-spacebetween a{
    color: #165DFF;
    font-size: 12px;
    text-decoration: none;
}
.layout-line-spacebetween a:hover{
    color: rgb(106, 150, 246);
    font-size: 12px;
    text-decoration: none;
}

.layout-right-line001{
  display: flex;
  flex-direction: column;
  justify-content: left;
  align-items: normal;
  flex: 2 0 0;
  background: #ffffff;
  border-radius: 4px;
  padding: 20px;
}
.layout-right-line002{
  display: flex;
  flex: 1 0 0;
  background: #ffffff;
  border-radius: 4px;

}
.layout-right-line003{
  display: flex;
  flex: 1 0 0;
  background: #ffffff;
  border-radius: 4px;
  padding: 20px;

}
.layout-line-wrap{
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}


</style>