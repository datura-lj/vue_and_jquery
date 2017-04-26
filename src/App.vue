<template>
  <div id="app">
    <button type="button" name="button" @click="change">按钮</button>
    <button type="button" name="button" @click="move">走你</button>
    <h2>{{ msg }}</h2>
    <div class="box">
      <span>我是一个普通的div</span>
    </div>
    <transition enter-active-class="zoomInLeft" leave-active-class="zoomOutRight">
      <div class="animated box" ref="div1" v-show="show">
          我能动起来
      </div>
    </transition>
  </div>
</template>

<script>
import $ from 'jquery';//引入jq
import fn from './assets/js/fn.js';//引入外部的fn.js文件

export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to vue',
      show: true
    }
  },
  methods: {
    change(){
      this.msg = 'div背景色变红了'
      $('.box').css('background-color','pink');
    },
    move(){
      this.show = !this.show;//用来配合动画（animate）使用
      this.$refs.div1.style.backgroundColor = 'lawngreen';
      //利用外部的fn.js中的rnd函数生成一个随机数
      let item =  $('.box:first span').html() + '；<br/>生成的随机数是：'+  fn.rnd(1,100);
      $('.box:first span').html(item);
    }
  }
}
</script>

<style scoped>
.box{
  width: 400px;
  height: 300px;
  margin: 50px auto;
  border: 1px solid #000;
  background-color: #fff;
  text-align: center;
  font-size: 30px;
}
</style>
