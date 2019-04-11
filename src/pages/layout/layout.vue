<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <van-row>
      <van-col span="8">span: 8</van-col>
      <van-col span="8">span: 8</van-col>
      <van-col span="8">span: 8</van-col>
    </van-row>
    <mybr/>
    <mybr/>
    <van-row>
      <van-col span="4">span: 4</van-col>
      <van-col span="10"
               offset="4">offset: 4, span: 10
      </van-col>
    </van-row>
    <mybr/>
    <mybr/>
    <van-row>
      <van-col offset="12"
               span="12">offset: 12, span: 12
      </van-col>
    </van-row>


  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "layout" ,
    components : {
      mybr
    } ,
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
<style src="./layout.css"
       scoped>

</style>
