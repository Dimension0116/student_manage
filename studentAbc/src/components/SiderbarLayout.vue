<template>
  <div class="sidebar">
    <div class="sidebar-item" v-for="(item, index) in siderbarItems" :key="item.title">
        <div class="sidebar-item-header" @click="toggleDropdown(index)">
            <div class="sidebar-item-title">
                <span class="iconfont" :class="[item.svg,isParentSelected[index]]" style="font-size: 18px;"></span>
                <span :class="isParentSelected[index]">{{ item.title }}</span>
            </div>    
            
            <span class="iconfont" :class="[iconClass[index],isParentSelected[index]]" style="font-size: 12px;"></span>
        </div>
        <div v-show="isDropdownOpen[index]" class="sidebar-dropdown">
            <div class="dropdown-item" v-for="(dropdownItem, dropdownindex) in item.dropdown" :key="dropdownindex" @click="selectedItem(index,dropdownindex)" :class="isSelectedBackground[index][dropdownindex]">
                <span style="width: 34px;"></span>
                <span style="font-size: 14px;" :class="isContentSelected[index][dropdownindex]">{{ dropdownItem }}</span>
                
            </div>
        </div>
    </div>
  </div>
</template>

<script setup>
    import { ref,onMounted } from 'vue'
    const siderbarItems = ref([
                {
                    svg: "icon-chart-bar",
                    title: "仪表盘",
                    dropdown: ["工作台", "实时监控"]
                },
                {
                    svg: "icon-data-view",
                    title: "数据可视化",
                    dropdown: ["分析页", "多维数据分析页"]
                },
                {
                    svg: "icon-column-vertical",
                    title: "列表页",
                    dropdown: ["查询表格", "卡片列表"]
                },
                {
                    svg: "icon-edit",
                    title: "表单页",
                    dropdown: ["分步表单", "分组表单"]
                },
                {
                    svg: "icon-browse",
                    title: "详情页",
                    dropdown: ["基础详情页"]
                }
            ]);
    const isDropdownOpen=ref([]);
    const iconClass=ref([]);
    const isParentSelected=ref([]);
    const isContentSelected=ref([]);
    const isSelectedBackground=ref([]);
    // const count=0;
    function initSelected(item,index){
        isParentSelected.value[index]='';
        item.dropdown.forEach((dropdownItem,dropdownindex)=>{
                isContentSelected.value[index][dropdownindex]='';
                isSelectedBackground.value[index][dropdownindex]='';
        })
    }
    function initVar(){

        siderbarItems.value.forEach((item,index)=>{
            isDropdownOpen.value.push(false);
            iconClass.value.push('icon-arrow-down-bold');
            isParentSelected.value.push('');
            isContentSelected.value.push([]); // 初始化为空数组
            isSelectedBackground.value.push([]); // 初始化为空数组
            item.dropdown.forEach((dropdownItem,dropdownindex)=>{
                isContentSelected.value[index].push('');
                isSelectedBackground.value[index].push('');
            })
        })
        console.log(isContentSelected.value);
    }
    
    initVar();
        // console.log(isDropdownOpen.value[0]);
    function toggleDropdown(index) {
        isDropdownOpen.value[index] = !isDropdownOpen.value[index];
        
        if(isDropdownOpen.value[index]){
            iconClass.value[index]='icon-arrow-up-bold';
            
        }else{
            iconClass.value[index]='icon-arrow-down-bold';

        }
    }
    function selectedItem(parentIndex,contentIndex){
        siderbarItems.value.forEach((item,index)=>{
            initSelected(item,index);
        })
        isParentSelected.value[parentIndex]='selected-color';
        console.log(isContentSelected.value);
        isContentSelected.value[parentIndex][contentIndex]='selected-color';
        isSelectedBackground.value[parentIndex][contentIndex]='selected-background-color';


    }
</script>

<style scoped>

.sidebar {
    width: 100%;
    height: 100%;
    background-color: #ffffff;
    display: flex;
    flex-direction: column;
    /* border-top: 1px solid #ccc; */
}

.sidebar-item {
    /* padding: 10px; */
    display: flex;
    flex-direction: column;
    /* border-bottom: 1px solid #ccc; */
}

.sidebar-item-header {
    padding: 9px 16px;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.sidebar-item-title {
    display: flex;
    justify-content: left;
    gap: 16px;
    font-size: 14px;
    align-items: center;
}

.sidebar-dropdown {
    /* margin-top: 5px; */
    padding: 4px;
    height: 100px;
    transition: height 2s ease;
}

.dropdown-item {
    padding: 9px 12px;
    border-radius: 4px;
    display: flex;
    cursor: pointer;
}
.dropdown-item:hover {
    background-color: #F2F3F5;
}
.selected-color{
    color: #165DFF;
}
.selected-background-color{
    background-color: #F2F3F5;
}
</style>