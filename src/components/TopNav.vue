<template>
    <ul class="navlist">
        <li><router-link to="/">推荐歌单</router-link></li>
        <li><router-link to="/hot">热歌榜</router-link></li>
        <li><router-link to="/search">搜索</router-link></li>
    </ul>
</template>
<style lang="less" scoped>
*{
    margin: 0;
    padding: 0;
}
    ul, ol{
        list-style: none;
    }
    a{
        text-decoration: none;
        color: #000;
    }
    .navlist{
        display: flex;
        border-bottom: 1px solid #ccc;
        li{
            flex: 1;
            a{
                display: inline-block;
                line-height: 40px;
                &.router-link-exact-active{
                    color: red;
                    border-bottom: 2px solid red;
                }
            }
        }
    }
</style>