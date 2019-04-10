<template>
  <view>
    <van-panel title="基础用法">
      <van-goods-action custom-class="goods-action" safe-area-inset-bottom="false">
        <van-goods-action-icon
          icon="chat-o"
          text="客服"
          open-type="contact"
        />
        <van-goods-action-icon
          icon="cart-o"
          text="购物车"
          @click="onClickIcon"
        />
        <van-goods-action-button
          text="加入购物车"
          type="warning"
          @click="onClickButton"
        />
        <van-goods-action-button
          text="立即购买"
          @click="onClickButton"
        />
      </van-goods-action>
    </van-panel>

    <van-panel title="图标提示">
      <van-goods-action custom-class="goods-action" safe-area-inset-bottom="false">
        <van-goods-action-icon icon="chat-o" text="客服"/>
        <van-goods-action-icon icon="cart-o" text="购物车" info="5"/>
        <van-goods-action-icon icon="shop-o" text="店铺"/>
        <van-goods-action-button text="加入购物车" type="warning"/>
        <van-goods-action-button text="立即购买"/>
      </van-goods-action>
    </van-panel>

    <van-toast id="van-toast"/>
  </view>
</template>
<script>
  import Toast from '../../../static/vant/toast/toast'

  export default {
    data() {
      return {}
    },
    methods: {
      onClickIcon() {
        Toast('点击图标');
      },

      onClickButton() {
        Toast('点击按钮');
      }
    }
  }
</script>
<style>
  .goods-action {
    position: relative !important;
  }

</style>
