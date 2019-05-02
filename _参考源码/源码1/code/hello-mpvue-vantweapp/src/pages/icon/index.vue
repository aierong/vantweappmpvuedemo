<template>
  <van-tabs :active="active" @change="onSwitch">
    <van-tab title="基础图标" custom-class="demo-tab-pane">
      <van-col v-for="item in icons.basic" :key="item" custom-class="col" span="6">
        <van-icon :name="item" size="32px" custom-class="icon"/>
        <div class="text">{{ item }}</div>
      </van-col>
    </van-tab>
    <van-tab title="线框风格" custom-class="demo-tab-pane">
      <van-col v-for="item in icons.outline" :key="item" custom-class="col" span="6">
        <van-icon :name="item" size="32px" custom-class="icon"/>
        <div class="text">{{ item }}</div>
      </van-col>
    </van-tab>
    <van-tab title="实底风格" custom-class="demo-tab-pane">
      <van-col v-for="item in icons.filled" :key="item" custom-class="col" span="6">
        <van-icon :name="item" size="32px" custom-class="icon"/>
        <view class="text">{{ item }}</view>
      </van-col>
    </van-tab>
  </van-tabs>
</template>
<script>
  import icons from '@/utils/icons-config'
  export default {
    data() {
      return{
        icons,
        active: 0
      }
    },
    methods: {
      onSwitch(event) {
        this.active = event.mp.detail.index
      }
    }
  }
</script>
<style>
  .col {
    text-align: center;
    height: 100px;
    float: none;
    display: inline-block;
    vertical-align: middle;
  }

  .icon {
    display: block;
    margin: 15px 0;
    color: #455a64;
  }

  .text {
    font-size: 12px;
    padding: 0 5px;
    line-height: 14px;
  }

  .demo-tab-pane {
    padding-top: 10px;
  }

</style>
