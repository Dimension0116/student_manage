<!-- 分栏布局 -->
<template>
    <div class="columnarParent">
        <div class="columnarHead">
            <slot name="head"></slot>
        </div>
        <div class="columnarContent">
            <div class="columnarContentLeft">
                <slot name="contentLeft"></slot>
            </div>
            <div class="columnarContentRight">
                <slot name="contentRight"></slot>
            </div>
        </div>
        
    </div>       
</template>

<script>

</script>

<style>
.columnarParent{
    display: flex;
    flex-direction: column;
    height: 100vh;
    width: 100vw;
}
.columnarHead{
    display: flex;
    flex-direction: row;
    height: 60px;
    /* background-color: darkred; */
}
.columnarContent{
    display: flex;
    flex:1 0 0;
    flex-direction: row;
}
.columnarContentLeft{
    display: flex;
    flex-direction: column;
    height: 100%;
    /* background-color: blanchedalmond; */
    width:200px;
}
.columnarContentRight{
    display: flex;
    flex:1 0 0;
    height: 100%;
    /* background-color: rgb(216, 243, 216); */
}
</style>