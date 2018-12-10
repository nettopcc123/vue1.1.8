<template>
    <div>
        <div class="swiper-container">
        <div class="swiper-slide" v-for="(value,key,index) in banlis">
            <div>
                <p></p>
                <p><img :src="value.log01" /></p>
                <p>{{ value.name01 }}</p>
            </div>
            <div>
                <p>{{ value.tit }}</p>
                <p>{{ value.num }}</p>
                <p>{{ value.cls }}</p>
            </div>
            <div>
                <p></p>
                <p><img :src="value.log02" /></p>
                <p>{{ value.name02 }}</p>
            </div>
        </div>
        </div>
        <!-- Add Pagination -->
        <div class="swiper-pagination01"></div>
        <!-- Add Arrows -->
        <div class="swiper-button-next01"></div>
        <div class="swiper-button-prev01"></div>
  </div>



</template>

<script>
import Swiper from 'swiper';
import 'swiper/dist/css/swiper.min.css';
export default {
   data(){
       return {
           banlis:[
            {
               tit:'英超联赛第14轮', 
               cls:'比赛结束',
               log01:require("./img/t_1.png"),
               log02:require("./img/t_2.png"),
               num:'1 - 0',
               name01:'利物浦',
               name02:'埃弗顿'
            },
            {
               tit:'英超联赛第15轮', 
               cls:'03:45',
               log01:require("./img/t_3.png"),
               log02:require("./img/t_4.png"),
               num:'VS',
               name01:'布莱顿',
               name02:'水晶宫'
            },
            {
               tit:'英超联赛第15轮', 
               cls:'03:45',
               log01:require("./img/t_5.png"),
               log02:require("./img/t_6.png"),
               num:'VS',
               name01:'伯恩茅斯',
               name02:'哈德斯菲尔德'
            },
            {
               tit:'英超联赛第15轮', 
               cls:'03:45',
               log01:require("./img/t_7.png"),
               log02:require("./img/t_8.png"),
               num:'VS',
               name01:'西汉姆联',
               name02:'卡迪夫城'
            }
           ]
       }
   },
   mounted:function(){
    this.$nextTick(function(){
    // var swiper = new Swiper('.swiper-container01', {
    //   slidesPerView: 2,
    //   spaceBetween: 10,
    //   slidesPerGroup: 1,
    //   loop: true,
    //   loopFillGroupWithBlank: true,
    //   pagination: {
    //     el: '.swiper-pagination01',
    //     clickable: true,
    //   },
    //   navigation: {
    //     nextEl: '.swiper-button-next01',
    //     prevEl: '.swiper-button-prev01',
    //   },
    // });

    })
  }
}
</script>
<style lang="scss" scoped>
@import "scss/base.scss";
    .swiper-container {
      width: 100%;
      height: 100%;
      padding-bottom:5px;
      background:#e6e6e6;
    }
    .swiper-wrapper{
        height: 100px;
    }
    .swiper-slide {
      text-align: center;
      font-size: 18px;
      background: #fff;
      color:#060606;
      width: 49%;
      float:left;
      /* Center slide text vertically */
      display: -webkit-box;
      display: -ms-flexbox;
      display: -webkit-flex;
      display: flex;
      -webkit-box-pack: center;
      -ms-flex-pack: center;
      -webkit-justify-content: center;
      justify-content: center;
      -webkit-box-align: center;
      -ms-flex-align: center;
      -webkit-align-items: center;
      align-items: center;
      border-radius: 0;
      margin-top:5px;
      height: 100px;
      border-radius: 0.05rem;
    }
    .swiper-slide:nth-child(2){
      float:right;
    }
    .swiper-slide:nth-child(4){
      float:right;
    }
    .swiper-slide div{
        display: block;
        clear: both;
        width: 100%;
        overflow: hidden;
        position: relative
    }
    .swiper-slide div p{
        line-height: 0.24rem;
    }
    .swiper-slide div p img{
        height: 0.41rem;
    }
    .swiper-container-horizontal{
        background:#fff;
        overflow: hidden;
        position: relative;
        z-index: 100;
    }
</style>