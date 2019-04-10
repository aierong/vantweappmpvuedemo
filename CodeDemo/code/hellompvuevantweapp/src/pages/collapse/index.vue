<template><div>
  <van-panel title="基础用法">
  <van-collapse :value=" active1 " data-key="active1" @change="onChange">
    <van-collapse-item :title=" title1 ">{{ content1 }}</van-collapse-item>
    <van-collapse-item :title=" title2 ">{{ content2 }}</van-collapse-item>
    <van-collapse-item :title=" title3 " disabled>{{ content3 }}</van-collapse-item>
  </van-collapse>
</van-panel>

<van-panel title="手风琴">
  <van-collapse :value=" active2 " data-key="active2" accordion @change="onChange">
    <van-collapse-item :title=" title1 ">{{ content1 }}</van-collapse-item>
    <van-collapse-item :title=" title2 ">{{ content2 }}</van-collapse-item>
    <van-collapse-item :title=" title3 ">{{ content3 }}</van-collapse-item>
  </van-collapse>
</van-panel>

<van-panel title="自定义标题内容">
  <van-collapse :value=" active3 " data-key="active3" @change="onChange">
    <van-collapse-item>
      <view slot="title">
        {{ title1 }}
        <van-icon name="question-o" custom-class="van-icon-question" />
      </view>
      {{ content1 }}
    </van-collapse-item>
    <van-collapse-item
      :title=" title2 "
      value="内容"
      icon="shop-o"
    >
      {{ content2 }}
    </van-collapse-item>
  </van-collapse>
</van-panel>
</div></template>
<script>
  export default {
    data(){
      return{
        active1: [0],
        active2: 0,
        active3: [],
        title1: '有赞微商城',
        title2: '有赞零售',
        title3: '有赞美业',
        content1: '提供多样店铺模板，快速搭建网上商城',
        content2: '网店吸粉获客、会员分层营销、一机多种收款，告别经营低效和客户流失',
        content3: '线上拓客，随时预约，贴心顺手的开单收银'
      }
    },
    methods:{
      onChange(event) {
        const { key } = event.mp.currentTarget.dataset;
        this[key]=event.mp.detail
      }
    }
  }
</script>
