<template>
    <div>
       <p style="text-align:left;margin-left:30px;">热门精选</p>
        <ul id="hotSong">
            <li>
                <router-link :to="{name:'single',params:{
                   singleName:'single'
                }}"><img src="../assets/1.jpg" alt="tupian" @click="getDataList"></router-link>
                <p class="descriptions">怀念装着5号电池的随身听</p>
            </li>
            <li>
                <img src="../assets/2.jpg" alt="tupian">
                <p class="descriptions">我就是音乐之王</p>
            </li>
            <li>
                <img src="../assets/3.jpg" alt="tupian">
                <p class="descriptions">怀念装着5号电池的随身听</p>
            </li>
            <li>
                <img src="../assets/4.jpg" alt="tupian">
                <p class="descriptions">怀念装着5号电池的随身听</p>
            </li>
            <li>
                <img src="../assets/5.jpg" alt="tupian">
                <p class="descriptions">怀念装着5号电池的随身听</p>
            </li>
            <li>
                <img src="../assets/6.jpg" alt="tupian">
                <p class="descriptions">怀念装着5号电池的随身听</p>
            </li>
            <li>
                <img src="../assets/7.jpg" alt="tupian">
                <p class="descriptions">怀念装着5号电池的随身听</p>
            </li>
            <li>
                <img src="../assets/8.jpg" alt="tupian">
                <p class="descriptions">怀念装着5号电池的随身听</p>
            </li>
        </ul>
    </div>
</template>
<script>
import jquery from "jquery"
import Vue from "vue"
import bus from "../bus/bus"
export default {
    data(){
        return {
            msg:"推荐模块"
        }
    },
    methods:{
        getDataList(){
           jquery.ajax({
               type:"GET",
               url:"https://api.imjad.cn/cloudmusic/?type=playlist&id=23464557",
               dataType:"json",
               success:function (data){
                   bus.$emit("playList",data)
               },
               error:function (err){
               }

           })
        }
    }
}
</script>
<style>
    #hotSong img{
        width:120px;
        height: 120px;
        overflow:hidden;
    }
    .descriptions{
        margin:0;
        margin-bottom:30px;
        font-size:14px;
        text-align:left;
    }
    #hotSong li{
        float:left;
        margin-right:50px;
        cursor: pointer;
        list-style:none;
        width:120px;
        height:120px;
        border:1px solid #000;
        margin-bottom:40px;
        margin-top:60px;
        /* background:green; */
    }
</style>


