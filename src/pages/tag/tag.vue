<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <van-tag>标签</van-tag>
    <van-tag type="danger">标签</van-tag>
    <van-tag type="primary">标签</van-tag>
    <van-tag type="success">标签</van-tag>
    <br>
    <van-tag plain>标签</van-tag>
    <van-tag plain
             type="danger">标签
    </van-tag>
    <van-tag plain
             type="primary">标签
    </van-tag>
    <van-tag plain
             type="success">标签
    </van-tag>
    <br>
    <van-tag round>标签</van-tag>
    <van-tag round
             type="danger">标签
    </van-tag>
    <van-tag round
             type="primary">标签
    </van-tag>
    <van-tag round
             type="success">标签
    </van-tag>
    <br>
    <van-tag mark>标签</van-tag>
    <van-tag mark
             type="danger">标签
    </van-tag>
    <van-tag mark
             type="primary">标签
    </van-tag>
    <van-tag mark
             type="success">标签
    </van-tag>
    <br>
    <van-tag color="#f2826a">标签</van-tag>
    <van-tag color="#f2826a"
             plain>标签
    </van-tag>
    <van-tag color="#7232dd">标签</van-tag>
    <van-tag color="#7232dd"
             plain>标签
    </van-tag>
    <van-tag color="#ffe1e1"
             text-color="#ad0000">标签
    </van-tag>
    <br>
    <van-tag>标签</van-tag>
    <van-tag color="#ffe1e1" size="medium">标签</van-tag>
    <van-tag size="large">标签</van-tag>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  export default {
    name : "tag" ,
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
<style src="./tag.css"
       scoped>

</style>
