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
                 @clickleft="onClickLeft2"
                 left-arrow>
      <van-icon @click="dj"
                name="search"
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
      backpage () {
        wx.navigateBack()
      } ,
      onClickLeft () {
        this.backpage();

      } ,
      onClickLeft2 () {
        this.backpage();
      } ,
      dj () {
        wx.showToast( {
          title : '点圈了' , //提示的内容,
          icon : 'success' , //图标,
          duration : 2000 , //延迟时间,
          mask : true , //显示透明蒙层，防止触摸穿透,
          success : res => {
            console.log( res )
          }
        } );
      } ,
      onClickRight () {
        console.log( 'onClickRight' )

        wx.showToast( {
          title : '点我了' , //提示的内容,
          icon : 'success' , //图标,
          duration : 2000 , //延迟时间,
          mask : true , //显示透明蒙层，防止触摸穿透,
          success : res => {
            console.log( res )
          }
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
<style src="./navbar.css">

</style>
