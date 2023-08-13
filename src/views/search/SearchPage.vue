<template>
    <div id="box_son">
        <div id="searcBox" :class="{ 'largepage': isLarge, 'app': !isLarge }">
            <div class="fangda">
                <img src="../../assets/redu/放大.png" alt="" v-show="fangdason" @click="dafang">
                <img src="../../assets/redu/缩小.png" alt="" v-show="suoxiaoson" @click="xiao">
            </div>
            <div id="searcBox_top">
                <div id="searcBox_top_son">
                    <SearcTop></SearcTop>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import SearcTop from '../../components/searcson/SearcTop.vue'  //头部子组件面
export default {
    components: {
        SearcTop,
    },
    data() {
        return {
            isLarge: false,
            fangdason: true,
            suoxiaoson: false

        }
    },
    methods: {

        dafang() {
            this.isLarge = !this.isLarge; // 切换页面大小
            this.suoxiaoson = true
            this.fangdason = false


        },
        xiao() {
            this.isLarge = !this.isLarge; // 切换页面大小
            this.fangdason = true
            this.suoxiaoson = false
        },
    }
}

</script>
<style lang="less" scoped>
#box_son {
    width: 100%;
    height: 100vh;
    background: url(https://img0.baidu.com/it/u=624935653,63733161&fm=253&app=120&size=w931&n=0&f=JPEG&fmt=auto?sec=1691946000&t=87a7ff58ddb49a0ae12cff9b03b0a259) no-repeat;
    background-size: 100% 100%;
}

.fangda {
    position: absolute;
    top: 0px;
    right: 0px;

    img {
        width: 25px;
        height: 30px;
    }
}

#searcBox {
    width: 100%;
    height: 100vh;
    background-color: #1c1c1ee8;
}

//这是头部页面
#searcBox_top {
    width: 100%;
    height: 60px;

    #searcBox_top_son {
        width: 100%;
        height: 50px;
        margin: auto;
    }
}

.largepage {
    width: 100%;
    height: 100vh;
    background-color: #1c1c1e;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    border-radius: 0px;
    transition: all 0.3s ease;
}

.app {
    width: 75% !important;
    // height: 90vh !important;
    overflow: auto;
    background-color: #1c1c1e;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    border-radius: 10px;
    transition: all 0.3s ease;
}

//右bian
.app::-webkit-scrollbar {
    display: none;
}
</style>