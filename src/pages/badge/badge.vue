<!--
作者:chenghao
Date: 2019/5/6
Time: 19:59
功能:
-->

<!-- html代码片段 -->
<template>

  <div>
    <van-badge-group active="active1"
                     @change="onChange1">
      <van-badge title="标签名称"/>
      <van-badge title="标签名称"
                 info="8"/>
      <van-badge title="标签名称"
                 info="99"/>
      <van-badge title="标签名称"
                 info="99+"/>
    </van-badge-group>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "badge" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        active1 : 0
      }
    } ,
    //方法
    methods : {
      onChange1 ( event ) {

        console.log( event.mp.detail )
        console.log( this.active1 )
        //最好手动赋值一下,要不值不是最新的
        this.active1 = event.mp.detail
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
<style src="./badge.css"
       scoped>
</style>
