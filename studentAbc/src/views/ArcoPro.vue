<script setup>
import ColumnarLayout from '../components/ColumnarLayout.vue'
import Navigation from '../components/Navigation.vue'
import LayoutLine from '../components/LayoutLine.vue'
import DropDownPanel from '../components/DropDownPanel.vue'
import SiderbarLayout from '../components/SiderbarLayout.vue'
import IconHeadSearch from '../components/icons/IconHeadSearch.vue'
import IconHeadSetting from '../components/icons/IconHeadSetting.vue'
import IconHeadLightDark from '../components/icons/IconHeadLightDark.vue'
import IconHeadLanguage from '../components/icons/IconHeadLanguage.vue'
import IconHeadHalfCircle from '../components/icons/IconHeadHalfCircle.vue'
import Crumbs from '../components/Crumbs.vue'

import { ref } from 'vue'
    const breadRoutes=ref([
        {
            name:'工作台',
            path:'/acropro/workplace'
        },
        {
            name:'实时监控',
            path:'/acropro/monitor'
        }
    ]);
</script>

<template>
    <ColumnarLayout style="background-color: #F7F8FA;">
        <template #head>
            <Navigation style="z-index: 999;">
                <template #headLeft>
                    <LayoutLine style="align-items: center;">
                        <img src="../assets/images/Arco@3x.png" style="width:32px;height: 32px;cursor:pointer;"/>
                        <span style="cursor:pointer;font-family: PingFang SC;font-size: 20px;font-weight: 500;line-height: 28px;letter-spacing: 0px;color: #1D2129;">Acro Pro</span>
                    </LayoutLine>
                </template>
                <template #headRight>
                    <LayoutLine style="align-items: center;">
                        <div class="headSvg">
                            <IconHeadSearch />
                        </div>
                        <div class="headSvg">  
                            <IconHeadLanguage />
                        </div>   
                        <div class="headSvg">
                            <IconHeadLightDark />
                        </div> 
                        <div class="headSvg">
                            <IconHeadHalfCircle />
                        </div>     
                        <div class="headSvg">
                            <IconHeadSetting />
                        </div>
                        <img src="../assets/images/Group1@3x.png" style="width:32px;height: 32px;cursor:pointer;"/>
                    </LayoutLine>
                </template>
                
            </Navigation>
        </template>
        <template #contentLeft>
            <!-- <DropDownPanel /> -->
            <SiderbarLayout />
        </template>
        <template #contentRight>
            <div style="padding: 20px;width: 100%;">
                <Crumbs :routes="breadRoutes"/>
                <RouterView />
            </div>
        </template>
    </ColumnarLayout>
</template>

<style>
    .headSvg{
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 50%;
        border:1px solid #F2F3F5;
        padding: 8px;
        cursor:pointer;
    }
</style>