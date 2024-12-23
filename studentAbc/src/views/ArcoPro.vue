<script setup>
import ColumnarLayout from '../components/ColumnarLayout.vue'
import Navigation from '../components/Navigation.vue'
import LayoutLine from '../components/LayoutLine.vue'
import IconHeadSearch from '../components/icons/IconHeadSearch.vue'
import IconHeadSetting from '../components/icons/IconHeadSetting.vue'
import IconHeadLightDark from '../components/icons/IconHeadLightDark.vue'
import IconHeadLanguage from '../components/icons/IconHeadLanguage.vue'
import IconHeadHalfCircle from '../components/icons/IconHeadHalfCircle.vue'
</script>

<template>
    <ColumnarLayout>
        <template #head>
            <Navigation>
                <template #headLeft>
                    <LayoutLine>
                        <img src="../assets/images/Arco@3x.png" style="width:32px;height: 32px;cursor:pointer;"/>
                        <span style="cursor:pointer;font-family: PingFang SC;font-size: 20px;font-weight: 500;line-height: 28px;letter-spacing: 0px;color: #1D2129;">Acro Pro</span>
                    </LayoutLine>
                </template>
                <template #headRight>
                    <LayoutLine>
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