<template>
    <div>
        <div class="mar">
            <vue-banner01d></vue-banner01d>
            <div class="hbut">
                <button>
                    <router-link :to="{ name: 'news'}">
                    <i class="iconfont icon-news"></i><span class="hbfont">新闻</span>
                    </router-link>
                </button>
                <button>
                    <router-link :to="{ name: 'htmlViewSample'}">
                        <i class="iconfont icon-race f22"></i><span class="hbfont">赛事</span>
                    </router-link>
                </button>
            </div>
            <vue-banner01a></vue-banner01a>
            <!-- 
            <vue-newlists1></vue-newlists1>
            <vue-banner01c></vue-banner01c>
            <vue-marquee></vue-marquee>
            <vue-banner01a></vue-banner01a> 
            -->
        </div>
        <h2 class="tit mt10"><i class="iconfont icon-news02"></i>热门新闻</h2>
        <vue-newlists8></vue-newlists8>
    </div>
</template>
<script>
    import marquee from './../components/marquee02';
    import newlists8 from './../components/newlists11';
    import newlists1 from './../components/new_h05';
    import banner01a from './../components/banner01';
    import banner01d from './../components/banner01_a';
    import banner01c from './../components/banner01_f';

    export default {
        data() {
            return {
                bdTokenUrl: 'https://m.sporttery.cn/app/zf/fb/livelist.html'
               // bdTokenUrl: 'http://tiyu.baidu.com/home' //https://m.sporttery.cn/app/zf/fb/livelist.html  https://m.sporttery.cn/app/zf/fb/livelist.html http://m.sporttery.cn/wap/dtc/fb_league_europe.html
            }
        },
        // created() {
        //     this.getUrl();
        //     this.$nextTick(()=>{
        //         this.getCode();
        //     });
        // },
        mounted(){

        },
        components: {
         'vue-marquee':marquee,
         'vue-newlists8':newlists8,
         'vue-newlists1':newlists1,
         'vue-banner01a':banner01a,
         'vue-banner01c':banner01c,
         'vue-banner01d':banner01d
        },
    }
</script>

<style lang="scss" scoped>
@import "scss/base.scss";
.child-view{
    height:100%;
}
.mar{
    overflow: hidden;
    background: #fff;
    z-index: 100;
    position: relative;
}
.tit{
    line-height: 0.36rem;
    background:#ffffff;
    color:#272727;
    text-indent: 0.1rem;
    border-bottom: 1px solid #d2d2d2
}
.tit i{
    float:left;
    font-size: 0.2rem;
}
.mt10{
    margin-top:10px;
}
.banner{
    background: url('img/bbg.png') center top no-repeat;
    background-size:100% auto;
}
.hbut{
    display: block;
    clear:both;
    overflow: hidden;
    margin-top:10px;
    margin-bottom:10px;
}
.hbut button:nth-child(1){
    width: 45%;
    float:left;
    color:#fff;
    background:#fe7073;
    border:1px solid #d44d50;
    box-shadow: 1px 1px 8px #888888;
    margin-left:3%;
    font-size: 0.18rem;
}
.hbut button:nth-child(2){
    width: 45%;
    float:right;
    color:#fff;
    background:#44a4f1;
    border:1px solid #2a7cbe;
    box-shadow: 1px 1px 8px #888888;
    margin-right:3%;
}
.hbut i{
    font-size: 0.24rem;
    float:left;
    padding-left:0.4rem;
}
.hbut span{
    line-height: 0.32rem;
    float:left;
}
.hbfont{
    padding-left:15px;
    font-size: 0.16rem;
}
.hbut a{
    color:#fff;
}
</style>