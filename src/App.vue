
<template>
  <div id="app">
    <header>

    </header>
    <div id="body">
      <div id="slideBar" class="lt">
        <p>推荐</p>
        <ul>
          <li>
            <router-link to="/findMusic">发现音乐</router-link>
          </li>
          <li>
            <router-link to="/personalFM">私人FM</router-link>
          </li>
          <li>
            <router-link to="/MV"> MV</router-link>
          </li>
          <li>
            <router-link to="/friends"> 朋友</router-link>
          </li>

        </ul>
        <p>我的音乐</p>
        <ul>
          <li>
            <router-link to="/iTunes">iTunes 音乐</router-link>
          </li>
          <li>
            <router-link to="/download">下载的音乐</router-link>
          </li>
        </ul>
        <p>创建的歌单</p>
        <ul>
          <li>
            <router-link to="/myFavorite">我喜欢的音乐</router-link>
          </li>

        </ul>
        <button id="btn" @click="getSongData">获取列表</button>
        <div>243234{{message}}</div>
        <!-- <div>
                    <p>
                      <img src="" alt="songPhoto">
                    </p>
                    <p>songName</p>
                  </div> -->

      </div>

      <div id="content" class="lt">
        <router-view></router-view>
      </div>
    </div>

  </div>
</template>

<script>
// 必须引入
import router from "./router/router"
import axios from "axios"
import jsonp from "jsonp"
export default {
  name: 'app',
  data() {
    return {
      msg: 'Welcome to Your Vue.js App',
      message: ""
    }
  },
  methods: {
    getSongData() {
      axios.get("/src/data.json").then(function(res) {
        alert("success")
        console.log(this.message = res.data.name)
      }.bind(this)).catch(function(err) {
        alert("error")
        console.log(err)
      })
    }
  }
}
</script>

<style scoped >
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100%;

  /* margin-top: 60px; */
}

a {
  text-decoration: none;
  color: #5C5C5C;
}

header {
  height: 100px;
  background: #ff0000;
}

#slideBar {
  width: 200px;
  background: #F5F5F7;
  height: 500px;
}

#content {
  flex: 1;
}

#body {
  overflow: hidden;
  display: flex;
  height: 100%;
}

.lt {
  float: left;
}

ul li {
  list-style: none;
  text-align: left;
  margin: 10px 0;
  cursor: pointer;
  font-size: 18px;
}

#slideBar>p {
  text-align: left;
  padding-left: 15px;
  font-size: 14px;
  padding-top: 10px;
}
</style>
