<template>
    <div>
        阿基搜的股份教案设计的
        
    </div>
</template>
<script>
import router from '../router/router'
import Vue from "vue"
import bus from "../bus/bus"
export default {
    data() {
        return {
        }
    },
    created: function() {
        console.log(Vue.prototype)
        bus.$off().$on("playList", function(res) {
            alert(2) 
            console.log(res)
        })
    },
    methods: {
       
    }
}
</script>
<style scoped>

</style>


