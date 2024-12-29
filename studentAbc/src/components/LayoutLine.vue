<!-- 线性布局 -->
<template>
    <div class="layoutLine">
        <slot></slot>
    </div>
</template>

<script>

</script>

<style>
.layoutLine{
    display: flex;
    flex-direction: row;
    /* align-items: center; */
    justify-content: left;
    gap: 1rem;
}
</style>