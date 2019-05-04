<!--
作者:chenghao
Date: 2019/5/4
Time: 19:39
功能:
-->

<!-- html代码片段 -->
<template>

  <div>
    <van-transition :show="show"
                    custom-class="block">
      内容
    </van-transition>
    <mybr/>
    <mybr/>
    <van-button @click="dj"
                size="normal">普通按钮
    </van-button>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "mytransition" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        show : false
      }
    } ,
    //方法
    methods : {
      dj () {
        this.show = !this.show;
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
       src="./mytransition.css">
</style>
