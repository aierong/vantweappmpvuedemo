<!--
作者:chenghao
Date: 2019/5/4
Time: 20:12
功能:
-->

<!-- html代码片段 -->
<template>

  <div>
    <view>基础使用</view>
    <!--
    如果没有设置 default-index
       会默认选择第1项-->
    <van-picker :columns="columns1"
                @change="onChange1"/>
    <mybr/>
    <mybr/>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "picker" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        columns1 : [
          '杭州' , '宁波' , '温州' , '嘉兴' , '湖州'
        ]
      }
    } ,
    //方法
    methods : {
      onChange1 () {
        //代码搞这里
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
       src="./picker.css">
</style>
