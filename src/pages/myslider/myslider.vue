<!--
作者:chenghao
Date: 2019/5/5
Time: 9:30
功能:
-->

<!-- html代码片段 -->
<template>

  <div>
    sliderSlider 滑块Slider 滑块
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "myslider" ,
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
<style src="./myslider.css"
       scoped>
</style>
