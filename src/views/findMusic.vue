<template>
    <div id="findMusic">
        <div id="findTitle">
            <!-- 推荐 -->
            <router-link to="/findMusic/recommend">推荐</router-link>
            <!-- 排行榜 -->
            <router-link to="/findMusic/ranking">排行榜</router-link>
            <!-- 歌单 -->
            <router-link to="/findMusic/songlist">歌单</router-link>
            <!-- 主播电台 -->
            <router-link to="/findMusic/station">主播电台</router-link>
            <!-- 最新音乐 -->
            <router-link to="/findMusic/newMusic">最新音乐</router-link>
        </div>
        <div>
            <keep-alive>
                <router-view></router-view>
                <!-- <router-view name="single1"></router-view> -->
            </keep-alive>
        </div>

    </div>
</template>
<script>
import router from '../router/router'
export default {
    data() {
        return {
        }
    }
}
</script>
<style scoped>
#findMusic {
    margin-top: 20px;
}

#findMusic a {
    text-decoration: none;
    color: #000;
    font-size: 18px;
    margin-left: 26px;
}

#findTitle {
    margin: 0 auto;
}

.router-link-active {
    color: #ff0000!important;
}
</style>


