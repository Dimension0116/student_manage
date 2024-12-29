<template>
  <div id="mn" style="width: 100%;height:289px;"></div>
</template>

<script setup>
import { onMounted,ref } from 'vue';
import * as echarts from 'echarts';
const chatRef = ref(null);

onMounted(()=>{
    chatRef.value = document.getElementById('mn');
    const myCharts=echarts.init(chatRef.value);
    const option = {
        xAxis: {
            type: 'category',
            boundaryGap: false,
            data: ['2024-12-25', '2024-12-26', '2024-12-27', '2024-12-28', '2024-12-29', '2024-12-30', '2024-12-31']
        },
        yAxis: {
            type: 'value'
        },
        grid: {
            top:'4%',
            left: '4%',
            right: '4%',
            bottom: '4%',
            containLabel: true
        },
        series: [
            {
            data: [520, 632, 901, 1034, 1290, 930, 720],
            type: 'line',
            smooth: 0.5,
            lineStyle: {
                color: {
                type: 'linear',
                x: 0,
                y: 0,
                x2: 1,
                y2: 0,
                colorStops: [
                    { offset: 0, color: '#1EE7FF' }, 
                    { offset: 1, color: '#6F42FB' }
                ]
                }
            },
            areaStyle: {
                color: {
                    type: 'linear',
                    x: 0,
                    y: 0,
                    x2: 0,
                    y2: 1,
                    colorStops: [
                    { offset: 0, color: '#117EFF' },
                    { offset: 1, color: 'white' }
                    ]
                },
            },
            symbol: 'emptyCircle', 
            showSymbol: false,
            symbolSize: 8
            }
        ],
        tooltip: {
            trigger: 'axis', 
            axisPointer: {
                type: 'line', // 设置轴指示器类型为直线，也就是悬浮时显示竖线
                lineStyle: {
                color: 'gray', // 设置竖线颜色，可按需调整
                width: 1, // 设置竖线宽度，可按需调整
                type: 'dashed' // 设置竖线样式为虚线，也可设置为'solid'（实线）等样式
                }
            },
            formatter: function (params) {
                // 自定义提示框内容的格式化函数，用于显示对应的数据
                return `日期：${params[0].name}<br>数值：${params[0].value}`;
            }
            }
        };
    myCharts.setOption(option);
})
</script>

<style>

</style>