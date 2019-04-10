<template>
  <div>
  <div title="按钮类型">
    <view class="row">
      <van-button type="primary">主要按钮</van-button>
      <van-button type="danger">危险按钮</van-button>
    </view>
    <van-button>默认按钮</van-button>
    <van-button type="warning">警告按钮</van-button>
  </div>

  <div title="朴素按钮">
    <van-button type="primary" plain>朴素按钮</van-button>
    <van-button type="danger" plain>朴素按钮</van-button>
  </div>

  <div title="禁用状态">
    <van-button type="primary" disabled>禁用状态</van-button>
    <van-button type="danger" disabled>禁用状态</van-button>
  </div>

  <div title="加载状态">
    <van-button loading type="primary" loading-class="loading" />
    <van-button loading type="danger" loading-class="loading" />
  </div>

  <div title="按钮形状">
    <van-button type="primary" square>方形按钮</van-button>
    <van-button type="danger" round>圆形按钮</van-button>
  </div>

  <div title="按钮尺寸">
    <van-button size="large" block>大号按钮</van-button>
    <van-button>普通按钮</van-button>
    <van-button size="small">小型按钮</van-button>
    <van-button size="mini">迷你按钮</van-button>
  </div>
  </div>
</template>
<script>
export default {

}
</script>
<style scoped>
  .loading {
    margin: 0 18px;
  }
  .row {
    height: 44px;
    margin-bottom: 15px;
  }
</style>
