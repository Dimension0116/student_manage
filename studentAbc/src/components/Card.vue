<template>
  <div class="card">
    <img :src="imgPath" style="width: 54px; height: 54px">
    <div class="card-content">
        <span>{{title}}</span>
        <div class="card-content-item">
            <span>{{content}}</span>
            <!-- <span>个</span> -->
        </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
    imgPath:{
        type: String,
        default: ''
    },
    title:{
        type: String,
        default: 'title'
    },
    content:{
        type: String,
        default: '999W+'
    }
})
</script>

<style scoped>
.card{
    display: flex;
    flex: 1 0 0;
    flex-direction: row;
    align-items: center;
    background-color: #ffffff;
    border-radius: 8px;
    padding: 20px;
    gap: 12px;
    
}

.card-content{
    display: flex;
    flex-direction: column;
    flex: 1 0 0;
}
.card-content-item{
    display: flex;
    flex-direction: row;
    align-items: center;
    font-size: 22px;
}
</style>