<template>
  <div class="siderbar">
    <div class="siderbar-item" v-for="item in siderbarItems" :key="item.title">
        <div class="sidebar-item-header" @click="toggleDropdown(index)">
                {{ item.title }}
                <span v-if="isDropdownOpen[index]" class="dropdown-icon">▼</span>
                <span v-else class="dropdown-icon">▶</span>
        </div>

    </div>
  </div>
</template>

<script setup>
    import { ref,created } from 'vue'
    const siderbarItems = ref([
                {
                    title: "菜单1",
                    dropdown: ["下拉项1-1", "下拉项1-2"]
                },
                {
                    title: "菜单2",
                    dropdown: ["下拉项2-1", "下拉项2-2", "下拉项2-3"]
                }
            ]);
    const isDropdownOpen=ref([]);
    created(()=>{
        isDropdownOpen.value = Array(siderbarItems.value.length).fill(false);
        console.log(isDropdownOpen.value[0]);
    })
    function toggleDropdown(index) {
        this.isDropdownOpen[index] = !this.isDropdownOpen[index];
    }

</script>

<style>

</style>