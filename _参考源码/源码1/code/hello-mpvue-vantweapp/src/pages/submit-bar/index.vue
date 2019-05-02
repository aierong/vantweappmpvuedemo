<template>
  <view>
    <van-panel title="基础用法">
      <van-submit-bar
        :price="3050"
        button-text="提交订单"
        @submit="onClickButton"
        custom-class="van-submit-bar"
        safe-area-inset-bottom="false"
      />
    </van-panel>

    <van-panel title="禁用状态">
      <van-submit-bar
        disabled
        :price="3050"
        button-text="提交订单"
        tip="您的收货地址不支持同城送, 我们已为您推荐快递"
        @submit="onClickButton"
        custom-class="van-submit-bar"
        safe-area-inset-bottom="false"
      />
    </van-panel>

    <van-panel title="加载状态">
      <van-submit-bar
        loading
        :price="3050"
        button-text="提交订单"
        @submit="onClickButton"
        custom-class="van-submit-bar"
        safe-area-inset-bottom="false"
      />
    </van-panel>

    <van-panel title="高级用法">
      <van-submit-bar
        :price="3050"
        button-text="提交订单"
        @submit="onClickButton"
        custom-class="van-submit-bar"
        tip="true"
        safe-area-inset-bottom="false"
      >
        <van-tag type="primary" custom-class="van-tag">标签</van-tag>
        <view slot="tip">
          您的收货地址不支持同城送
          <text class="edit-address" @tap="onClickLink">修改地址</text>
        </view>
      </van-submit-bar>
    </van-panel>

    <van-toast id="van-toast"/>
  </view>
</template>
<script>
  import Toast from '../../../static/vant/toast/toast'
  export default {
    data() {
      return {
      }
    },
    methods: {
      onClickButton() {
        Toast('点击按钮');
      },
      onClickLink() {
        Toast('修改地址');
      }
    }
  }
</script>
<style>
  .van-submit-bar {
    position: relative !important;
  }
  .edit-address {
    color: #1989fa;
  }
  .van-tag {
    margin-left: 15px;
  }
</style>
