<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <div></div><div></div>
    <van-icon name="close"/>
    <van-icon name="https://b.yzcdn.cn/vant/icon-demo-1126.png"/>
    <div></div>
    <van-icon name="chat"
              info="9"/>
    <van-icon size="40px"
              name="chat"
              info="99+"/>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  export default {
    name : "icon" ,
    //数据模型
    data () {
      return {
        msg : ''
      }
    } ,
    //方法
    methods : {
      //methodsname() {
      //代码搞这里
      //},

    } ,
    //计算属性
    computed : {
      //name() {
      //代码搞这里
      //return this.data;
      //}
    } ,
    //生命周期(mounted)
    mounted () {

    } ,
  }
</script>

<!-- 样式代码片段  scoped -->
<style src="./icon.css"
       scoped>

</style>
