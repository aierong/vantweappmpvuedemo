<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <van-panel title="标题"
               desc="描述信息"
               status="状态a">
      <view>内容</view>
    </van-panel>
    <mybr/>
    <mybr/>

    <van-panel title="标题"
               desc="描述信息"
               status="状态2"
               use-footer-slot>
      <view>内容</view>
      <!--
      加个样式把按钮搞右边去
      -->
      <view style="text-align: right;"
            slot="footer">
        <van-button @click="dja"
                    size="small">按钮A
        </van-button>
        <van-button @click="djb"
                    size="small"
                    type="danger">按钮B
        </van-button>
      </view>
    </van-panel>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "mypanel" ,
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
      dja () {
        wx.showToast( {
          title : 'a' , //提示的内容,
          icon : 'success' , //图标,
          duration : 2000 , //延迟时间,
          mask : true , //显示透明蒙层，防止触摸穿透,
          success : res => {
            console.log( res )
          }
        } );
      } ,
      djb () {
        wx.showToast( {
          title : 'b' , //提示的内容,
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
<style src="./mypanel.css"
       scoped>

</style>
