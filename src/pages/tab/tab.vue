<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <van-tabs :active="active"
              @change="onChange">
      <van-tab title="标签 1">内容 1</van-tab>
      <van-tab title="标签 2">内容 2</van-tab>
      <van-tab title="标签 3">内容 3</van-tab>
      <van-tab title="标签 4">内容 4</van-tab>
    </van-tabs>
    <br><br><br>
    <!--    多于 4 个标签时，Tab 可以横向滚动-->
    <div>Tab可横向滚动</div>
    <van-tabs :active=" active ">
      <van-tab title="标签 1">内容 1</van-tab>
      <van-tab title="标签 2">内容 2</van-tab>
      <van-tab title="标签 3">内容 3</van-tab>
      <van-tab title="标签 4">内容 4</van-tab>
      <van-tab title="标签 5">内容 5</van-tab>
      <van-tab title="标签 6">内容 6</van-tab>
      <van-tab title="标签7">内容7</van-tab>
      <van-tab title="标签8">内容8</van-tab>
      <van-tab title="标签9">内容9</van-tab>
    </van-tabs>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  export default {
    name : "tab" ,
    //数据模型
    data () {
      return {
        //从0开始的
        active : 2
      }
    } ,
    //方法
    methods : {
      onChange ( event ) {
        //代码搞这里
        console.log( event )

        //选择的索引
        console.log( event.mp.detail.index )
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
       src="./tab.css">

</style>
