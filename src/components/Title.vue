<template>
    <div class="t1">
        <h2><slot></slot></h2>
    </div>
</template>
<script>
export default {
    name:"Title"
}
</script>
<style lang="less" scoped>
    .t1{
        text-align: left;
        h2{
            position: relative;
            padding-left:10px;
            // border-left: 3px solid red;
            margin: 20px 0;
            &::after{
                position: absolute;
                content: "";
                display: block;
                width: 2px;
                height: 16px;
                left: 0;
                top: 50%;
                margin-top: -9px;
                background-color: red;
            }
        }
    }
</style>