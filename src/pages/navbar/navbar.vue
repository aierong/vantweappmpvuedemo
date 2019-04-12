<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <!--    @click-left="onClickLeft"-->
    <!--    @click-right="onClickRight"-->
    <van-nav-bar title="标题"
                 left-text="返回"
                 right-text="按钮"
                 left-arrow
                 @clickleft="onClickLeft"
                 @clickright="onClickRight"/>
    <mybr/>
    <mybr/>

    <van-nav-bar title="标题"
                 left-text="返回"
                 left-arrow>
      <van-icon name="search"
                slot="right"/>
    </van-nav-bar>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "navbar" ,
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
      onClickLeft () {
        wx.navigateBack()
        //wx.navigateBack()
      } ,
      onClickRight () {
        console.log( 'onClickRight' )
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
<style src="./navbar.css">

</style>
