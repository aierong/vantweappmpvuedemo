<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <mybr/>
    <mybr/>
    <van-loading/>
    <van-loading color="red"/>
    <mybr/>
    <mybr/>
    <van-loading type="spinner"/>
    <van-loading type="spinner"
                 color="green"/>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>

  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "loading" ,
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
<style src="./loading.css"
       scoped>
</style>
