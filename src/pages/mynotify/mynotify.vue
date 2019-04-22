<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <mybr/>
    <mybr/>
    <van-button @click="showNotify">显示消息通知</van-button>
    <van-button @click="showNotify2">显示自定义消息通知</van-button>
    <!--
    注意要配一个van-notify,才会显示提示

    -->
    <van-notify id="van-notify"/>
    <van-notify id="customselector"/>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  // 代码中也要引用
  // 注意引用路径
  import Notify from '../../../static/vant/notify/notify';

  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "mynotify" ,
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
      showNotify () {
        //代码搞这里
        Notify( '通知内容' );
      } ,
      showNotify2 () {
        //duration	持续时间   默认:3000
        //color	字体颜色
        //backgroundColor	背景色
        Notify( {
          duration : 1000 ,
          text : '通知内容' ,
          selector : '#customselector' ,
          backgroundColor : '#1989fa'
        } );
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
       src="./mynotify.css">

</style>
