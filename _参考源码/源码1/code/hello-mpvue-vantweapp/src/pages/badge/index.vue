<template>
  <van-panel title="基础用法">
    <view class="container">
      <van-badge-group @change="onChange" custom-class="group">
        <van-badge title="第一步"/>
        <van-badge title="第二步" info="8"/>
        <van-badge title="第三步" info="99"/>
        <van-badge title="第四步" info="99+"/>
      </van-badge-group>
    </view>
  </van-panel>
</template>
<script>
  export default {
    data(){
      return{

      }
    },
    methods:{
      onChange(event) {
        wx.showToast({
          icon: 'none',
          title: `切换至第${event.mp.detail}项`
        });
      }
    }
  }
</script>
<style>
  .container {
    width: auto;
    margin: 0 15px;
    padding: 20px 0;
    background-color: #75fff4;
  }

  .group {
    margin: 0 auto;
  }

</style>
