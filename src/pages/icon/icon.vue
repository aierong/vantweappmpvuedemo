<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <mybr/>
    <van-icon name="close"/>
    <mybr/>
    <van-icon name="https://b.yzcdn.cn/vant/icon-demo-1126.png"/>
    <mybr/>
    <van-icon name="chat"
              info="9"/>
    <mybr/>
    <van-icon size="40px"
              name="chat"
              color="red"
              info="99+"/>
    <mybr/>
    <van-icon name="chat"
              size="32px"/>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "icon" ,
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
<style src="./icon.css">

</style>
