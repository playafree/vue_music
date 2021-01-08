<template>
    <div>
        <HotMusicItem :musicList='musicList'></HotMusicItem>
    </div>
</template>
<script>
import HotMusicItem from '../components/HotMusicItem'
export default {
    name:'hot',
    components:{
        HotMusicItem
    },
    data(){
        return {
            hotMusicList:[],
            musicId:[],
            musicList:[]
        }
    },
    beforeRouteEnter(to,from,next){
        next(vm=>{
            vm.$http.get('/playlist/detail?id=3778678').then(data=>{
                for(let i in data.data.playlist.trackIds){
                    if(i<20){
                        vm.musicId.push(data.data.playlist.trackIds[i].id);
                    }
                }
                vm.musicId.forEach((v) => {
                    vm.$http.get(`/song/detail?ids=${v}`).then(data=>{
                        vm.musicList.push(data.data.songs[0])
                    })
                });
            })
        })
    },
}
// /playlist/detail?id=3778678
</script>