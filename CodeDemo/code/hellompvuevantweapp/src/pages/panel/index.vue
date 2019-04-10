<template>
  <div>
    <van-panel  title="基础用法">
      <van-panel title="标题" desc="描述信息" status="状态">
        <view class="content">内容</view>
      </van-panel>
    </van-panel>

    <van-panel title="高级用法">
      <van-panel title="标题" desc="描述信息" status="状态" use-footer-slot>
        <view class="content">内容</view>
        <view slot="footer" class="footer">
          <van-button size="small" class="demo-margin-right">按钮</van-button>
          <van-button size="small" type="danger">按钮</van-button>
        </view>
      </van-panel>
    </van-panel>
  </div>
</template>
<script>
  export default {
    data() {
      return {}
    },
    methods: {}
  }
</script>
<style>
  .content {
    padding: 20px;
    font-size: 16px;
  }

  .footer {
    text-align: right;
  }
</style>
