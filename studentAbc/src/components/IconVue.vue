<template>
    <div class="icon-vue-root">
        <div class="icon-vue-img-div" v-if="path!=''">
            <img :src="path">
        </div>
        <span style="font-size: 12px; color: #424E66;">{{ title }}</span>
    </div>
</template>

<script setup>
const props = defineProps({
    path: String,
    title: String
})
</script>

<style scoped>
.icon-vue-root{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 64px;
    height: 64px;
    gap: 4px;
    cursor: pointer;
    padding: 4px 7px;

}
.icon-vue-img-div{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 32px;
    padding: 7px;
    height: 32px;
    background: #F7F8FA;
    border-radius: 6px;
}
</style>