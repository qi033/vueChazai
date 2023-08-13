<template>
    <div class="hello">
        <div>
            <div class="tabs">
                <div v-for="(item, index) in tabs" :key="index" @click="changeTab(index)"
                    :class="{ active: activeTab === index }">
                    <p>{{ item.title }}</p>
                </div>
            </div>

            <div id="searcBox_shenzi">
                <!-- 这是左边盒子 -->
                <div id="searcBox_shenzi_zuo">
                    <div class="searcBox_shenzi_zuo_son">
                        <input type="text" placeholder="搜索" v-model="search" @keyup="searchfun()" />
                        <vuedraggable class="wrapper">
                            <transition-group>
                                <ul v-for="(item, index) in flag ? newarr : subscribe" :key="index" v-show="activeTab == 0">
                                    <li :class="{ selected: selectedIndex === index }" @click="selectLi(index)">
                                        <img :src="item.img" alt="" />
                                        <a href="#" @click="changeToWeChat">{{ item.name }}</a>
                                        <span @click="del(index)">删除</span>
                                    </li>
                                </ul>
                            </transition-group>
                        </vuedraggable>
                    </div>

                    <ul v-if="activeTab == 1">
                        <li><a href="#" @click="changeToWeChat">微博</a><span>⭐</span></li>
                        <li><a href="#" @click="WeChat">微信</a><span>⭐</span></li>
                        <li><a href="#" @click="changeToDouyin">百度</a><span>⭐</span></li>
                        <li><a href="#" @click="Zhihu">知乎</a><span>⭐</span></li>
                        <li><a href="#" @click="Tiktok">抖音</a><span>⭐</span></li>
                    </ul>
                    <ul v-if="activeTab == 2">
                        <li><a href="#" @click="changeToWeChat">微博</a><span>⭐</span></li>
                        <li><a href="#" @click="WeChat">微信</a><span>⭐</span></li>
                        <li><a href="#" @click="Zhihu">知乎</a><span>⭐</span></li>
                    </ul>
                    <ul v-if="activeTab == 3">
                        <li><a href="#" @click="heatyi">36氮</a><span>⭐</span></li>
                        <li><a href="#" @click="heat2">少数派</a><span>⭐</span></li>
                        <li><a href="#" @click="heat3">虎嗅网</a><span>⭐</span></li>
                    </ul>
                    <ul v-if="activeTab == 4">
                        <li><a href="#" @click="heat4">哗哩哗哩</a><span>⭐</span></li>
                        <li><a href="#" @click="Tiktok">抖音</a><span>⭐</span></li>
                        <li><a href="#" @click="heat6">煎蛋</a><span>⭐</span></li>
                    </ul>
                    <ul v-if="activeTab == 5">
                        <li><a href="#" @click="heat7">吾爱破解</a><span>⭐</span></li>
                        <li><a href="#" @click="heat8">百度贴吧</a><span>⭐</span></li>
                        <li><a href="#" @click="heat9">腾讯新闻</a><span>⭐</span></li>
                    </ul>
                    <ul v-if="activeTab == 6">
                        <li><a href="#" @click="heat10">淘宝·天猫</a><span>⭐</span></li>
                        <li><a href="#" @click="heat11">什么值得买</a><span>⭐</span></li>
                        <li><a href="#" @click="heat12">今日热卖</a><span>⭐</span></li>
                    </ul>
                    <ul v-if="activeTab == 7">
                        <li><a href="#" @click="heat13">雪球</a><span>⭐</span></li>
                        <li><a href="#" @click="heat14">第一财经</a><span>⭐</span></li>
                        <li><a href="#" @click="heat15">财新网</a><span>⭐</span></li>
                    </ul>
                    <ul v-if="activeTab == 8">
                        <h3 style="color: aliceblue; margin-top: 30px">
                            抱歉你还没有开通权限
                        </h3>
                    </ul>
                    <ul v-if="activeTab == 9">
                        <h3 style="color: aliceblue; margin-top: 30px">
                            抱歉你还没有开通权限
                        </h3>
                    </ul>
                    <ul v-if="activeTab == 10">
                        <h3 style="color: aliceblue; margin-top: 30px">
                            抱歉你还没有开通权限
                        </h3>
                    </ul>
                    <ul v-if="activeTab == 11">
                        <h3 style="color: aliceblue; margin-top: 30px">
                            抱歉你还没有开通权限
                        </h3>
                    </ul>
                    <ul v-if="activeTab == 12">
                        <h3 style="color: aliceblue; margin-top: 30px">
                            抱歉你还没有开通权限
                        </h3>
                    </ul>
                    <ul v-if="activeTab == 13">
                        <h3 style="color: aliceblue; margin-top: 30px">
                            抱歉你还没有开通权限
                        </h3>
                    </ul>
                    <ul v-if="activeTab == 14">
                        <h3 style="color: aliceblue; margin-top: 30px">
                            抱歉你还没有开通权限
                        </h3>
                    </ul>
                    <ul v-if="activeTab == 15">
                        <h3 style="color: aliceblue; margin-top: 30px">
                            抱歉你还没有开通权限
                        </h3>
                    </ul>
                    <ul v-if="activeTab == 16">
                        <h3 style="color: aliceblue; margin-top: 30px">
                            抱歉你还没有开通权限
                        </h3>
                    </ul>
                    <ul v-if="activeTab == 17">
                        <h3 style="color: aliceblue; margin-top: 30px">
                            抱歉你还没有开通权限
                        </h3>
                    </ul>
                    <ul v-if="activeTab == 18">
                        <h3 style="color: aliceblue; margin-top: 30px">
                            抱歉你还没有开通权限
                        </h3>
                    </ul>
                    <ul v-if="activeTab == 19">
                        <h3 style="color: aliceblue; margin-top: 30px">
                            抱歉你还没有开通权限
                        </h3>
                    </ul>
                    <ul v-if="activeTab == 20">
                        <h3 style="color: aliceblue; margin-top: 30px">
                            抱歉你还没有开通权限
                        </h3>
                    </ul>
                </div>
                <transition name="fade">
                    <!-- 这是右边盒子 -->
                    <div id="searcBox_shenzi_you">
                        <!-- 上边选中状态 -->
                        <div id="searcBox_shenzi_you_top">
                            <p>
                                <span v-show="ooopppwww"> {{ selectedData }}</span>
                                <span v-show="yincanqwe">{{ platform }}</span>.热搜榜
                            </p>
                        </div>
                        <div v-if="activeTab == 0">
                            <div class="searcBox_shenzi_you_son">
                                <ul v-for="(item, index) in flag ? newarr : outside" :key="index">
                                    <li class="wocao2">
                                        <div class="fangkuai" :class="{
                                            color1: index === 0,
                                            color2: index === 1,
                                            color3: index === 2,
                                        }">
                                            {{ item.id }}
                                        </div>
                                        <div class="fangkuai">
                                            <a :title="item.name" href="#">{{ item.name }}</a>
                                        </div>
                                        <div class="fangkuai">
                                            <span>{{ item.heat }}</span>
                                        </div>
                                    </li>
                                </ul>
                            </div>
                        </div>
                        <div v-if="activeTab == 1">
                            <div class="searcBox_shenzi_you_son">
                                <ul v-for="(item, index) in searchone" :key="index">
                                    <li class="wocao2">
                                        <div class="fangkuai" :class="{
                                            color1: index === 0,
                                            color2: index === 1,
                                            color3: index === 2,
                                        }">
                                            {{ item.id }}
                                        </div>
                                        <div class="fangkuai">
                                            <a :title="item.name" href="#">{{ item.name }}</a>
                                        </div>
                                        <div class="fangkuai">
                                            <span>{{ item.heat }}</span>
                                        </div>
                                    </li>
                                </ul>
                            </div>
                        </div>

                        <div v-if="activeTab == 2">
                            <div class="searcBox_shenzi_you_son">
                                <ul v-for="(item, index) in searchtwo" :key="index">
                                    <li class="wocao2">
                                        <div class="fangkuai" :class="{
                                            color1: index === 0,
                                            color2: index === 1,
                                            color3: index === 2,
                                        }">
                                            {{ item.id }}
                                        </div>
                                        <div class="fangkuai">
                                            <a :title="item.name" href="#">{{ item.name }}</a>
                                        </div>
                                        <div class="fangkuai">
                                            <span>{{ item.heat }}</span>
                                        </div>
                                    </li>
                                </ul>
                            </div>
                        </div>
                        <div v-if="activeTab == 3">
                            <div class="searcBox_shenzi_you_son">
                                <ul v-for="(item, index) in three" :key="index">
                                    <li class="wocao2">
                                        <div class="fangkuai" :class="{
                                            color1: index === 0,
                                            color2: index === 1,
                                            color3: index === 2,
                                        }">
                                            {{ item.id }}
                                        </div>
                                        <div class="fangkuai">
                                            <a :title="item.name" href="#">{{ item.name }}</a>
                                        </div>
                                        <div class="fangkuai">
                                            <span>{{ item.heat }}</span>
                                        </div>
                                    </li>
                                </ul>
                            </div>
                        </div>
                        <div v-if="activeTab == 4">
                            <div class="searcBox_shenzi_you_son">
                                <ul v-for="(item, index) in four" :key="index">
                                    <li class="wocao2">
                                        <div class="fangkuai" :class="{
                                            color1: index === 0,
                                            color2: index === 1,
                                            color3: index === 2,
                                        }">
                                            {{ item.id }}
                                        </div>
                                        <div class="fangkuai">
                                            <a :title="item.name" href="#">{{ item.name }}</a>
                                        </div>
                                        <div class="fangkuai">
                                            <span>{{ item.heat }}</span>
                                        </div>
                                    </li>
                                </ul>
                            </div>
                        </div>
                        <div v-if="activeTab == 5">
                            <div class="searcBox_shenzi_you_son">
                                <ul v-for="(item, index) in five" :key="index">
                                    <li class="wocao2">
                                        <div class="fangkuai" :class="{
                                            color1: index === 0,
                                            color2: index === 1,
                                            color3: index === 2,
                                        }">
                                            {{ item.id }}
                                        </div>
                                        <div class="fangkuai">
                                            <a :title="item.name" href="#">{{ item.name }}</a>
                                        </div>
                                        <div class="fangkuai">
                                            <span>{{ item.heat }}</span>
                                        </div>
                                    </li>
                                </ul>
                            </div>
                        </div>
                        <div v-if="activeTab == 6">
                            <div class="searcBox_shenzi_you_son">
                                <ul v-for="(item, index) in six" :key="index">
                                    <li class="wocao2">
                                        <div class="fangkuai" :class="{
                                            color1: index === 0,
                                            color2: index === 1,
                                            color3: index === 2,
                                        }">
                                            {{ item.id }}
                                        </div>
                                        <div class="fangkuai">
                                            <a :title="item.name" href="#">{{ item.name }}</a>
                                        </div>
                                        <div class="fangkuai">
                                            <span>{{ item.heat }}</span>
                                        </div>
                                    </li>
                                </ul>
                            </div>
                        </div>
                        <div v-if="activeTab == 7">
                            <div class="searcBox_shenzi_you_son">
                                <ul v-for="(item, index) in seven" :key="index">
                                    <li class="wocao2">
                                        <div class="fangkuai" :class="{
                                            color1: index === 0,
                                            color2: index === 1,
                                            color3: index === 2,
                                        }">
                                            {{ item.id }}
                                        </div>
                                        <div class="fangkuai">
                                            <a :title="item.name" href="#">{{ item.name }}</a>
                                        </div>
                                        <div class="fangkuai">
                                            <span>{{ item.heat }}</span>
                                        </div>
                                    </li>
                                </ul>
                            </div>
                        </div>
                        <div v-if="activeTab == 8">
                            <h1 title="这个页面你还没有开通权限">
                                这个页面你还没有开通2222权限
                            </h1>
                        </div>
                        <div v-if="activeTab == 9">
                            <h1>这个页面你还没有开通权限</h1>
                        </div>
                        <div v-if="activeTab == 10">
                            <h1>这个页面你还没有开通权限</h1>
                        </div>
                        <div v-if="activeTab == 11">
                            <h1>这个页面你还没有开通权限</h1>
                        </div>
                        <div v-if="activeTab == 12">
                            <h1>这个页面你还没有开通权限</h1>
                        </div>
                        <div v-if="activeTab == 13">
                            <h1>这个页面你还没有开通权限</h1>
                        </div>
                        <div v-if="activeTab == 14">
                            <h1>这个页面你还没有开通权限</h1>
                        </div>
                        <div v-if="activeTab == 15">
                            <h1>这个页面你还没有开通权限</h1>
                        </div>
                        <div v-if="activeTab == 16">
                            <h1>这个页面你还没有开通权限</h1>
                        </div>
                        <div v-if="activeTab == 17">
                            <h1>这个页面你还没有开通权限</h1>
                        </div>
                        <div v-if="activeTab == 18">
                            <h1>这个页面你还没有开通权限</h1>
                        </div>
                        <div v-if="activeTab == 19">
                            <h1>这个页面你还没有开通权限</h1>
                        </div>
                        <div v-if="activeTab == 20">
                            <h1>这个页面你还没有开通权限</h1>
                        </div>
                    </div>
                </transition>
            </div>
        </div>
    </div>
</template>

<script>
import vuedraggable from "vuedraggable";

import { outside } from "@/api/search"; //订阅
import { searchone } from "@/api/searchone"; //全部

import { searchtwo } from "@/api/searchtwo"; //综合
import { three } from "@/api/three"; //科技

import { four } from "@/api/four"; //娱乐
import { five } from "@/api/five"; //社区页面
import { six } from "@/api/six"; //订阅
import { seven } from "@/api/seven"; //订阅

export default {
    components: { vuedraggable },
    name: "HelloWorld",
    data() {
        return {
            newarr: [],
            search: "",
            flag: false,
            selectedData: "",
            yincanqwe: false,
            ooopppwww: true,
            outside: outside,
            searchone: searchone,
            searchtwo: searchtwo,
            three: three,
            four: four,
            five: five,
            six: six,
            seven: seven,
            selectedIndex: null,
            subscribe: [
                {
                    img: "https://files.codelife.cc/topsearch/Jb0vmloB1G.png",
                    name: "百度",
                },
                {
                    img: "https://files.codelife.cc/topsearch/KqndgxeLl9.png",
                    name: "微博",
                },
                {
                    img: "https://files.codelife.cc/topsearch/mproPpoq6O.png",
                    name: "知乎",
                },
            ],
            platform: "微博",
            activeTab: 0,
            tabs: [
                { title: "我的订阅" },
                { title: "全部" },
                { title: "综合" },
                { title: "科技" },
                { title: "娱乐" },
                { title: "社区" },
                { title: "购物" },
                { title: "财经" },
                { title: "大学" },
                { title: "日报" },
                { title: "地方门户" },
                { title: "影视" },
                { title: "阅读" },
                { title: "游戏" },
                { title: "体育" },
                { title: "产品" },
                { title: "开发" },
                { title: "设计" },
                { title: "应用" },
                { title: "汽车" },
                { title: "安全" },
            ],
        };
    },
    mounted() {
        // 在mounted生命周期钩子函数中使用引入的JS文件
        console.log(this.outside);
    },
    methods: {
        //搜索
        searchfun() {
            if (this.search != "") {
                this.flag = true;
                this.newarr = this.subscribe.filter((item) => {
                    if (item.name.includes(this.search)) {
                        return item;
                    }
                });
            } else {
                this.flag = false;
            }
            console.log(11);
        },
        //选中状态
        selectLi(index) {
            this.selectedIndex = index;
            this.selectedData = this.flag
                ? this.newarr[index].name
                : this.subscribe[index].name;
            this.yincanqwe = false;
            this.ooopppwww = true;
        },
        //删除
        del(index) {
            if (confirm("确定删除吗")) {
                this.subscribe.splice(index, 1);
            }
        },
        heatyi() {
            this.platform = "36氮";
            this.yincanqwe = true;
        },
        heat2() {
            this.platform = "少数派";
            (this.yincanqwe = true), (this.ooopppwww = false);
        },
        heat3() {
            this.platform = "虎嗅网";
            this.yincanqwe = true; (this.ooopppwww = false);
        },
        heat4() {
            this.platform = "哗哩哗哩";
            this.yincanqwe = true; (this.ooopppwww = false);
        },
        heat6() {
            this.platform = "煎蛋"; (this.ooopppwww = false);
            this.yincanqwe = true;
        },
        heat7() {
            this.platform = "吾爱破解"; (this.ooopppwww = false);
            this.yincanqwe = true;
        },
        heat8() {
            this.platform = "百度贴吧"; (this.ooopppwww = false);
            this.yincanqwe = true;
        },
        heat9() {
            this.platform = "腾讯新闻"; (this.ooopppwww = false);
            this.yincanqwe = true;
        },
        heat10() {
            this.platform = "淘宝·天猫"; (this.ooopppwww = false);
            this.yincanqwe = true;
        },
        heat11() {
            this.yincanqwe = true;
            this.platform = "什么值得买"; (this.ooopppwww = false);
        },
        heat12() {
            this.platform = "今日热卖"; (this.ooopppwww = false);
            this.yincanqwe = true;
        },
        heat13() {
            this.platform = "雪球"; (this.ooopppwww = false);
            this.yincanqwe = true;
        },
        heat14() {
            this.platform = "第一财经"; (this.ooopppwww = false);
            this.yincanqwe = true;
        },
        heat15() {
            this.platform = "财新网"; (this.ooopppwww = false);
            this.yincanqwe = true;
        },
        Zhihu() {
            this.platform = "知乎";
            this.yincanqwe = true; (this.ooopppwww = false);
        },
        Tiktok() {
            this.platform = "抖音";
            this.yincanqwe = true; (this.ooopppwww = false);
        },
        WeChat() {
            this.platform = "微信";
            this.yincanqwe = true; (this.ooopppwww = false);
        },
        changeToWeChat() {
            this.platform = "微博";
            this.yincanqwe = true; (this.ooopppwww = false);
        },
        changeToDouyin() {
            this.platform = "百度"; (this.ooopppwww = false);
            this.yincanqwe = true;
        },
        changeTab(index) {
            this.activeTab = index;
            this.yincanqwe = true; (this.ooopppwww = false);
        },
    },
};
</script>

<style scoped lang="less">
.selected-li {
    background-color: pink !important;
}

.selected {
    background-color: #33c5c5;
}

.wrapper {
    display: flex;
    justify-content: center;
    width: 100%;
}

// .item {

//     width: 300px;

//     height: 50px;

//     background-color: #42b983;

//     color: #ffffff;

// }

.color1 {
    background-color: #fe2d46 !important;
}

.color2 {
    background-color: #ff6600 !important;
}

.color3 {
    background-color: #faa90e !important;
}

#searcBox_shenzi_zuo {
    width: 95%;

    height: 100%;
    border-right: 0.5px solid #252527;

    text-align: none;

    // ul li:hover span {
    //     display: block;

    // }

    // ul li span {
    //     display: none;
    // }

    ul li {
        width: 200px;
        margin-top: 10px;
        height: 50px;
        line-height: 50px;
        padding-left: 20px;
        color: #fff;
        display: flex;
        justify-content: space-around;
        margin-left: -30px;
    }

    a {
        width: 155px;
        color: #fff;
        text-decoration: none;
        // margin-left: -70px;
    }

    input:hover {
        border: 1px solid #ddd;
    }

    input {
        width: 95%;
        background: #25252c;
        color: #fff;

        border: none;
        font-size: 1px;
        width: 90%;
        border-radius: 10px;
        padding-left: 10px;
        height: 25px;
        margin-top: 10px;
    }
}

ul li {
    list-style: none;
}

//这是身子页面
#searcBox_shenzi {
    border-top: 1px solid #2d2d30;

    width: 100%;
    display: flex;
    justify-content: space-between;
    margin-top: 20px;

    //zuobian

    #searcBox_shenzi_zuo {
        width: 20%;
        height: 90vh;
        margin-left: 25px;

        .searcBox_shenzi_zuo_son {
            img {
                width: 20px;
                height: 20px;
                margin-top: 15px;
                margin-left: -10px;
            }

            li {
                display: flex;
                justify-content: space-around;
            }
        }
    }

    //右bian
    #searcBox_shenzi_you::-webkit-scrollbar {
        display: none;
    }

    #searcBox_shenzi_you {
        width: 80%;
        height: 90vh;
        margin-right: 10px;
        color: #fff;
        line-height: 60px;
        overflow: auto;

        ul li .fangkuai:nth-child(3) {
            text-align: right;
        }

        ul li .fangkuai:nth-child(2):hover a {
            color: #33c5c5;
        }

        .fangkuai {
            width: 40%;
        }

        .searcBox_shenzi_you_son .fangkuai:nth-child(1) {
            width: 25px;
            height: 25px;
            background-color: #25252c;
            margin-left: 8px;
            text-align: center;
            margin-top: 18px;
            line-height: 25px;
            border-radius: 5px;
        }

        .searcBox_shenzi_you_son .fangkuai:nth-child(2) {
            margin-left: 5px;
        }

        .searcBox_shenzi_you_son .fangkuai:nth-child(3) {
            color: #909090;
            margin-left: 180px;
        }

        a {
            color: #fff;
            text-decoration: none;
            // margin-left: -70px;
        }

        ul li {
            display: flex;
            justify-content: space-around;
        }

        #searcBox_shenzi_you_top {
            border-bottom: 2px solid #414243;
            width: 100%;
            height: 50px;

            p {
                padding-left: 10px;
            }
        }
    }
}

.tabs {
    width: 95%;
    height: 55px;
    line-height: 55px;
    margin: auto;
    display: flex;
    justify-content: space-between;
    font-family: "宋体";
    font-size: 14px;
    color: #ffff;
    border-bottom: 3px solid #414243;

    p:hover {
        color: #33c5c5;
    }
}

.tab-content {
    margin-top: 10px;
}

.active {
    color: #33c5c5;
    border-bottom: 3px solid #33c5c5;
    z-index: 999;
}
</style>
