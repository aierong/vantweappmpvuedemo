<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <div>自做demo</div>
    <van-row class="user-links">
      <van-col span="6">
        <van-icon name="pending-payment"
                  size="36px"/>
        <br>待付款
      </van-col>
      <van-col span="6">
        <van-icon name="bag"
                  size="36px"/>
        <br>待接单
      </van-col>
      <van-col span="6">
        <van-icon name="fire"
                  size="36px"/>
        <br>待发货
      </van-col>
      <van-col span="6">
        <van-icon name="logistics"
                  size="36px"/>
        <br>待发货
      </van-col>
    </van-row>
    <mybr/>
    <mybr/>
    <div>九宫格</div>
    <van-row class="user-links">
      <van-col span="8">
        <van-icon @click="dj"
                  name="pending-payment"
                  size="36px"/>
        <br>待付款
      </van-col>
      <van-col span="8">
        <van-icon @click="dj"
                  name="bag"
                  size="36px"/>
        <br>待接单
      </van-col>
      <van-col span="8">
        <van-icon @click="dj"
                  name="fire"
                  size="36px"/>
        <br>点我
      </van-col>

    </van-row>
    <van-row class="user-links">
      <van-col span="8">
        <van-icon name="play"
                  size="36px"/>
        <br>待付款
      </van-col>
      <van-col span="8">
        <van-icon name="bag"
                  size="36px"/>
        <br>待接单
      </van-col>
      <van-col span="8">
        <van-icon name="fire"
                  size="36px"/>
        <br>待发货
      </van-col>

    </van-row>
    <van-row class="user-links">
      <van-col span="8">
        <van-icon name="chat"
                  size="36px"/>
        <br>待付款
      </van-col>
      <van-col span="8">
        <van-icon name="close"
                  size="36px"/>
        <br>待接单
      </van-col>
      <van-col span="8">
        <van-icon name="success"
                  size="36px"/>
        <br>待发货
      </van-col>

    </van-row>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "layoutdemo" ,
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
      dj () {
        //代码搞这里
        wx.showToast( {
          title : '我醒了' , //提示的内容,
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
<style src="./layoutdemo.css">

</style>
