<!--
作者:chenghao
Date: 2019/5/5
Time: 9:58
功能:
-->

<!-- html代码片段 -->
<template>

  <div>
    <view>基础用法</view>
    <van-stepper :value="val1"
                 @change="onChange1"/>
    <mybr/>
    <mybr/>
    <view>高级用法</view>
    <!--
    每次加减为1，可以对组件设置step、min、max属性
    -->
    <van-stepper :value="val2"
                 integer
                 min="5"
                 max="40"
                 step="2"
                 @change="onChange2"
    />
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "stepper" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        val1 : 11 ,
        val2 : 12
      }
    } ,
    //方法
    methods : {
      onChange1 ( event ) {

        console.log( event )

        this.val1 = event.mp.detail
      } ,
      onChange2 ( event ) {
        console.log( event )

        this.val2 = event.mp.detail
      }
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
       src="./stepper.css">
</style>
