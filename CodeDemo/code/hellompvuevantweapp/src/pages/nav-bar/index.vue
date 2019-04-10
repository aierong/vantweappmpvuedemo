<template><div>
<van-panel title="基础用法">
  <van-nav-bar
    title="标题"
    left-text="返回"
    right-text="按钮"
    left-arrow
    @clickLeft="onClickLeft"
    @clickRight="onClickRight"
  />
</van-panel>

<van-panel title="高级用法">
  <van-nav-bar title="标题" left-text="返回" left-arrow>
    <van-icon name="search" slot="right" custom-class="icon" />
  </van-nav-bar>
</van-panel>
</div></template>
<script>
  export default {
    data(){
      return{

      }
    },
    methods:{
      onClickLeft() {
        wx.showToast({ title: '点击返回', icon: 'none' });
      },

      onClickRight() {
        wx.showToast({ title: '点击按钮', icon: 'none' });
      }
    },
    created(){

    }
  }
</script>
<style>
  .icon {
    color: #1989fa;
  }

</style>
