<!--
作者:chenghao
Date: 2019/5/6
Time: 19:49
功能:
-->

<!-- html代码片段 -->
<template>

  <div>
    <view>基本使用</view>
    <van-switch :checked="checked1"
                @change="onChange1"/>
    <mybr/>
    <mybr/>
    <view>自己定义大小颜色</view>
    <van-switch @change="onChange2"
                :checked="checked2"
                size="48px"
                active-color="#07c160"
                inactive-color="#f44"
    />
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "switch" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        checked1 : true ,
        checked2 : false
      }
    } ,
    //方法
    methods : {
      onChange1 ( event ) {
        console.log( event.mp.detail )
        //最好手动赋值一下,要不值不是最新的
        this.checked1 = event.mp.detail;
      } ,
      onChange2 ( event ) {
        this.checked2 = event.mp.detail;
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
       src="./switch.css">
</style>
