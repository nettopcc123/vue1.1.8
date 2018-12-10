<template>
<div id="feedback">
  <h2 class="uitit_b"><i class="iconfont icon-message02 uif"></i>留言内容</h2>
  <ul class="fedlis">
    <li v-for="(value, key) in feedlist">
        <span class="fename">{{ value.name }}</span>
        <span class="fecon">{{ value.fmess }}</span>
    </li>
  </ul>
  <h2 class="uitit_a"><i class="iconfont uic"></i>意见反馈</h2>
  <textarea v-bind:maxlength="140" @input="descArea" v-model="introduct" name="abstract" id="abstract" placeholder="您的意见，会让我们更优秀。" class="ftext"></textarea>
  <span class="num-desc">您还可以输入 {{Surplus}} 个字符 / 共 140 个字符</span>
  <button class="fbut" @click="isloadshow()">提交</button>
 </div> 
 </template>
<script>
import Vue from 'vue';
import 'vue2-toast/lib/toast.css';
import Toast from 'vue2-toast';
import $ from 'jquery';
Vue.use(Toast);
export default {
  data(){
    return{
      Surplus:140,
      introduct:'',
      feedlist:[]
    }
  },
  created: function(){
    this.$nextTick(() => {//在下次 DOM 更新循环结束之后执行延迟回调
        console.log(localStorage.getItem('feedcon'));
    })
  },
  methods:{
    descArea(){
      var textVal = this.introduct.length;
      this.Surplus = 140 - textVal;
    },
    isloadshow() {
      this.$store.commit('isloadshow');
      let uname = localStorage.getItem('u');
      let ucon = this.introduct;
      if(uname == '登入/注册'){
        name = '游客';
      }else{
        name = uname;
      }
      setTimeout(() => {
        this.isloadhid();
        this.feedlist.push({'name':name,'fmess':ucon});
        let newfeed = this.feedlist.toString();
        localStorage.setItem('feedcon',newfeed);
      },2000)
    },
    isloadhid() {
      this.$store.commit('isloadhid');
      this.$toast.center('提交成功');
    },
    routerback: function () {
      this.$router.back(-1)
    }
  }
}
</script>

<style lang="scss" scoped>
@import "scss/base.scss";
#feedback{
  text-align: center;
}
.ftext{
  display: inline-block;
  width: 90%;
  height: 1.32rem;
  line-height: 1.5;
  padding: 0.04rem 0.07rem;
  font-size: 0.12rem;
  border: 0.01rem solid #dcdee2;
  border-radius: 0.04rem;
  color: #515a6e;
  background-color: #fff;
  background-image: none;
  position: relative;
  cursor: text;
  transition: border .2s ease-in-out,background .2s ease-in-out,box-shadow .2s ease-in-out;
  margin: 0.1rem auto;
}
.fbut{
  width: 94%
}
.num-desc{
  display: block;
  text-align: left;
  width: 94%;
  margin:0 auto 0.2rem;
  color:#8f8f8f
}
.uitit{
    display: block;
    line-height: 0.36rem!important;
    border-left: 0.03rem solid $bgColor!important;
    padding-left:0.15rem;
    font-size: 0.18rem;
    text-align: left;
    background:#fff!important;
}
.uitit_a{
    display: block;
    line-height: 0.36rem!important;
    padding-left:0.15rem;
    font-size: 0.18rem;
    text-align: center;
    background:#fff !important;
    border-bottom: 1px solid #e8e8ec;
    color:#202020;
    font-weight: normal;
}
.uitit_b{
    display: block;
    line-height: 0.36rem!important;
    padding-left:0.15rem;
    font-size: 0.16rem;
    text-align: center;
    border-bottom: 1px solid #e8e8ec;
    color:#5b5b5b;
    font-weight: normal;
    margin-top:30px;
}
.uic{
    position: absolute;
    left:0.1rem;
    line-height: 0.4rem;
    font-size:0.24rem;
    font-weight: normal;
}
.uif{
    position: absolute;
    left:0.1rem;
    line-height: 0.4rem;
    font-size:0.2rem;
    font-weight: normal;
}
.fedlis{
  display: block;
  clear:both;
  overflow: hidden;
  min-height: 50px;
}
.fedlis li{
  display: block;
  clear:both;
  overflow: hidden;
  line-height: 0.24rem;
}
.fename{
  float:left;
  width:25%;
  text-align: left;
  color:#858585;
  text-indent: 0.1rem;
}
.fecon{
  float:right;
  width: 70%;
  padding:0px;
  margin:0px;
  text-align: left;
}
</style>
