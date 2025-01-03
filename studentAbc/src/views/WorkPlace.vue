<script setup>
import CardVue from '../components/Card.vue'
import LayoutLine from '../components/LayoutLine.vue'
import EchartsVue from '@/components/EchartsVue.vue';
import IconVue from '../components/IconVue.vue'
import CarouselVue from '@/components/CarouselVue.vue';
import { ref } from 'vue'
const imgPathCarsel = ref([
    '@/assets/images/img1.png',
    '@/assets/images/img2.png',
    '@/assets/images/img3.png',
    '@/assets/images/img4.png',
  ])
</script>
<template>
  <div class="root">
    <LayoutLine style="flex:1 0 0;">
     <LayoutLine class="root-left">
      <LayoutLine class="layout-line001">
        <span style="font-size: 20px;font-weight: 500;color: #1D2129;">欢迎回来，Xiao！</span>
        <LayoutLine class="card-layout-line">
          <CardVue imgPath="../src/assets/images/线上总内容.png" title="线上总内容" content="1000W+"/>
          <CardVue imgPath="../src/assets/images/投放中内容.png" title="投放中内容" content="100"/>
          <CardVue imgPath="../src/assets/images/日新增评论.png" title="日新增评论" content="999"/>
          <CardVue imgPath="../src/assets/images/较昨日新增.png" title="较昨日新增" content="8889"/>
        </LayoutLine>
        <LayoutLine class="layout-line-spacebetween">
          <div>
            <span style="font-size: 16px;font-weight: 500;color: #1D2129;">内容数据</span>
            <span style="font-size: 12px;color: #4E5969;">（近7日）</span>
          </div>
          <a href="#">查看更多</a>
        </LayoutLine>
        <LayoutLine class="layout-line002">
          <EchartsVue/>
        </LayoutLine>
      </LayoutLine>
      <LayoutLine class="layout-line002">
        
      </LayoutLine>  
      </LayoutLine>
      <LayoutLine class="root-right">
        <LayoutLine class="layout-right-line001">
          <LayoutLine class="layout-line-spacebetween">
            <span style="font-size: 16px;font-weight: 500;color: #1D2129;">快捷入口</span>
            <a href="#">管理</a>
          </LayoutLine>
          <LayoutLine class="layout-line-wrap">
            <IconVue path="../src/assets/svgs/bookmark.svg" title="内容管理"/>
            <IconVue path="../src/assets/svgs/bookmark.svg" title="内容管理"/>
            <IconVue path="../src/assets/svgs/bookmark.svg" title="内容管理"/>
            <IconVue path="../src/assets/svgs/bookmark.svg" title="内容管理"/>
            <IconVue path="../src/assets/svgs/bookmark.svg" title="内容管理"/>
          </LayoutLine>
          <div style="height: 0;width: 100%;border: solid 1px #F2F3F5;"></div>
          <LayoutLine class="layout-line-spacebetween">
            <span style="font-size: 16px;font-weight: 500;color: #1D2129;">最近访问</span>
            <a href="#">管理</a>
          </LayoutLine>
          <LayoutLine class="layout-line-wrap">
            <IconVue path="../src/assets/svgs/bookmark.svg" title="内容管理"/>
            <IconVue path="../src/assets/svgs/bookmark.svg" title="内容管理"/>
            <IconVue path="../src/assets/svgs/bookmark.svg" title="内容管理"/>
          </LayoutLine>
        </LayoutLine>
        <LayoutLine class="layout-right-line002">
          <CarouselVue :data="imgPathCarsel"/>
        </LayoutLine>
        <LayoutLine class="layout-right-line003">
        </LayoutLine>
        <LayoutLine class="layout-right-line003">
        </LayoutLine>

      </LayoutLine>
    </LayoutLine>
    
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