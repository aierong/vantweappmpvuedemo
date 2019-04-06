<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <van-button type="default">默认按钮</van-button>
    <br><br>
    <van-button type="primary">主要按钮</van-button>
    <br><br>
    <van-button type="info">信息按钮</van-button>
    <br><br>
    <van-button type="warning">警告按钮</van-button>
    <br><br>
    <van-button @click="dj"
                type="danger">危险按钮
    </van-button>

  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  export default {
    name : "button" ,
    //数据模型
    data () {
      return {
        msg : ''
      }
    } ,
    //方法
    methods : {
      dj () {
        console.log( 'dj' )
      } ,

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
<style scoped
       src="./button.css">

</style>
