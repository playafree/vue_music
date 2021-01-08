<template>
    <ul class="hotMusic">
            <router-link v-for="item in musicList" :key="item.id" tag="li" to="/">
                <div class="left">
                    <div>{{item.name}}</div>
                    <p>{{item.ar[0].name}} - {{item.al.name}}</p>
                </div>
                <div class="right">
                    <span></span>
                </div>
            </router-link>
    </ul>
</template>
<script>
export default {
    name:'HotMusicItem',
    props:{
        musicList:Array,
    },
    filters:{
        addName(value){
            let name = [];
            for(let index in value){
                name.push(value[index].name);
            }
            return name.join('/');
        }
    }
}
</script>
<style lang="less" scoped>
    .hotMusic{
        li{
            display: flex;
            margin-top: 8px;
            padding-left: 10px;
            div.left{
                flex: 1;
                text-align: left;
                border-bottom: 1px solid #ddd;
                div{
                    font-size: 17px;
                    color: black;
                }
                p{
                    font-size: 12px;
                    color: #888;
                    margin: 4px 0;
                    i{
                        width: 12px;
                        height: 8px;
                        display: inline-block;
                        background-image: url('../assets/index_icon_2x.png');
                        background-size: 166px 97px;
                        background-position: 0px 0px;
                        margin-right: 5px;
                    }
                }
            }
            div.right{
                padding: 0 5px;
                display: flex;
                align-items: center;
                span{
                    display: inline-block;
                    height: 22px;
                    width: 22px;
                    background-image: url('../assets/index_icon_2x.png');
                    background-size: 166px 97px;
                    background-position: -24px 0;
                }
                border-bottom: 1px solid #ddd;
            }
        }
    }
</style>