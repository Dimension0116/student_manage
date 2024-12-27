<!-- 面包屑 -->
<template>
  <div class="breadcrumbs">
    <div class="breadcrumb-item separator" v-for="(item, index) in breadcrumbItems" :key="index">
      <router-link :to="item.link" class="router-link-class">{{ item.name }}</router-link>
      <span v-if="index !== breadcrumbItems.length - 1">/</span>
    </div>
  </div>
</template>

<script setup>
  import { ref,watch,onMounted } from 'vue';
  const breadcrumbItems = ref([]);
  //定义输入参数
  const props = defineProps({
    routes:{
        type:Array,
        default:()=>[]
    }
  });
  //生成面包屑项
  const generateBreadcrumbItems = (routes) => {
    const items = [];
    routes.forEach(routes=>{
        items.push({
            name:routes.name,
            link:routes.path
        });
    });
    breadcrumbItems.value=items;
  }
    //监听路由变化
    watch(() => props.routes,(newRoutes)=>{
        generateBreadcrumbItems(newRoutes);
    })

    //挂载组件生成面包屑项
    onMounted(()=>{
        generateBreadcrumbItems(props.routes);
    })



</script>

<style scoped>
.breadcrumbs {
  display: flex;
  align-items: center;
  justify-content: left;

}
.breadcrumb-item{
  display: flex;
  align-items: center;
  justify-content: left;
  
}

.router-link-class{
    color:#4E5969;
    background-color: transparent;
}
.currentA{
    color:#1D2129;
}

.separator{
    color:#C9CDD4;
}

</style>