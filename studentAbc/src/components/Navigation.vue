<!-- 导航栏 -->
<template>
        <div class="navigationHead">
            <slot name="headLeft"></slot>
            <slot name="headRight"></slot>

        </div>
</template>

<script>

</script>

<style>
.navigationHead{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    height: 100%;
    padding: 0 16px;
    background-color: white;
    box-shadow: 0px 4px 10px 0px rgba(78, 89, 105, 0.06);
}
</style>