<!--
作者:chenghao
Date: 2019/5/6
Time: 20:12
功能:
-->

<!-- html代码片段 -->
<template>

  <div>
    <view>基本使用</view>
    <!--    fixed	是否固定在底部-->
    <van-tabbar :fixed="isfixed"
                :active="active1"
                @change="onChange1">
      <van-tabbar-item icon="home-o">标签</van-tabbar-item>
      <van-tabbar-item icon="search"
                       dot>标签
      </van-tabbar-item>
      <van-tabbar-item icon="friends-o"
                       info="5">标签
      </van-tabbar-item>
      <van-tabbar-item icon="setting-o"
                       info="20">标签
      </van-tabbar-item>
    </van-tabbar>
    <mybr/>
    <mybr/>
    <mybr/>
    <mybr/>
    <view>自定义颜色</view>
    <van-tabbar :active="active2"
                :fixed="isfixed"
                active-color="#07c160"
                @change="onChange2">
      <van-tabbar-item icon="home-o">标签</van-tabbar-item>
      <van-tabbar-item icon="search">标签</van-tabbar-item>
      <van-tabbar-item icon="friends-o">标签</van-tabbar-item>
      <van-tabbar-item icon="setting-o">标签</van-tabbar-item>
    </van-tabbar>
    <mybr/>
    <mybr/>
    <mybr/>
    <mybr/>
    <view>自定义图标</view>
    <van-tabbar :active="active3"
                :fixed="isfixed"
                @change="onChange3">
      <van-tabbar-item info="3">
        <image slot="icon"
               src="/static/img/Add_32x32.png"
               mode="aspectFit"/>
        <image slot="icon-active"
               src="/static/img/Add_active.png"
               mode="aspectFit"/>
        自定义
      </van-tabbar-item>
      <van-tabbar-item icon="search">标签</van-tabbar-item>
      <van-tabbar-item icon="setting-o">标签</van-tabbar-item>
    </van-tabbar>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "mytabbar" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        isfixed : false ,
        active1 : 0 ,

        active2 : 0 ,
        active3 : 0 ,
        icon : {
          normal : '//img.yzcdn.cn/icon-normal.png' ,
          active : '//img.yzcdn.cn/icon-active.png'
        }
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
      onChange2 ( event ) {
        console.log( event.mp.detail )
        console.log( this.active1 )
        //最好手动赋值一下,要不值不是最新的
        this.active2 = event.mp.detail
      } ,
      onChange3 ( event ) {
        console.log( event.mp.detail )
        console.log( this.active1 )
        //最好手动赋值一下,要不值不是最新的
        this.active3 = event.mp.detail
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
       src="./mytabbar.css">
</style>
