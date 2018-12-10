<template>
    <div>
        <div class="mar">
            <img :src="require('./../components/img/ban_xiao.jpg')" alt="">
            <vue-newlists1></vue-newlists1>
            <vue-banner01c></vue-banner01c>
            <!-- <vue-marquee></vue-marquee>
            <vue-banner01a></vue-banner01a> -->
        </div>
        <h2 class="tit mt10"><i class="iconfont icon-news02"></i>热门新闻</h2>
        <vue-newlists8></vue-newlists8>
    </div>
</template>
<script>
    import marquee from './../components/marquee02';
    import newlists8 from './../components/newlists9';
    import newlists1 from './../components/new_h05';
    import banner01a from './../components/banner01_d';
    import banner01d from './../components/banner01_e';
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
</style>