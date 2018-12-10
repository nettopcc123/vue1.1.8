<template>
    <div>
        <div class="iftop">
        <iframe ref="iframe" id="bdIframe" :src="bdTokenUrl" frameborder="0" scrolling="auto" width="100%" height="100%" ></iframe>
        </div>
    </div>
</template>

<script>
import newlists8 from './../components/newlists10';
import $ from 'jquery';
    export default {
        data() {
            return {
                bdTokenUrl: 'https://m.sporttery.cn/app/zf/fb/livelist.html' //https://m.sporttery.cn/app/zf/fb/livelist.html  https://m.sporttery.cn/app/zf/fb/livelist.html
            }
        },
        // created() {
        //     this.getUrl();
        //     this.$nextTick(()=>{
        //         this.getCode();
        //     });
        // },
        mounted(){
            /**
             * iframe-宽高自适应显示   
             */

            const oIframe = document.getElementById('bdIframe');
            const deviceWidth = document.documentElement.clientWidth;
            const deviceHeight = document.documentElement.clientHeight;
            oIframe.style.width =  '100%'; //数字是页面布局宽度差值
            oIframe.style.height = '100%'; //数字是页面布局高度差
        },
        components: {
         'vue-newlists8':newlists8
        }
    }
</script>

<style lang="scss">
@import "scss/base.scss";
.child-view{
    height:100%;
}
.iftop{
    height: 100%;
    margin-top:0px;
}
.bghid{
    height: 6060px;
    background:rgba(255,255,255,0);
    width: 100%;
    position: absolute;
    top:0px;
    left:0px;
}
</style>
