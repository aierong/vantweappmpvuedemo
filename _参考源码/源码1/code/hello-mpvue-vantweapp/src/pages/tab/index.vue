<template>
  <div>
    <van-panel title="基础用法">
      <van-tabs active="1" @change="onChange">
        <van-tab
          v-for="item in [1,2,3,4]"
          :key="index"
          :title="'标签' + item"
        >
          <view class="content">
            {{ '内容' + item }}
          </view>
        </van-tab>
      </van-tabs>
    </van-panel>

    <van-panel title="自定义标题">
      <van-tabs active="1" @change="onChange">
        <van-tab
          v-for="item in [1,2,3,4]"
          :key="index"
          :title="'标签' + item"
          title-style="font-size: 16px; font-weight: bold; index === 0 ? 'text-decoration: line-through;' : ''"
          :dot="index === 1"
          :info="index === 2 ? 99 : null"
        >
          <view class="content">
            {{ '内容' + item }}
          </view>
        </van-tab>
      </van-tabs>
    </van-panel>

    <van-panel title="横向滚动">
      <van-tabs>
        <van-tab
          v-for="item in [1,2,3,4,5,6]"
          :key="index"
          :title="'标签' + item"
        >
          <view class="content">
            {{ '内容' + item }}
          </view>
        </van-tab>
      </van-tabs>
    </van-panel>

    <van-panel title="禁用标签">
      <van-tabs @disabled="onClickDisabled">
        <van-tab
          v-for="item in [1,2,3]"
          :key="index"
          :disabled="index === 1"
          :title="'标签' + item"
        >
          <view class="content">
            {{ '内容' + item }}
          </view>
        </van-tab>
      </van-tabs>
    </van-panel>

    <van-panel title="样式风格">
      <van-tabs type="card">
        <van-tab
          v-for="item in [1,2,3]"
          :key="index"
          :title="'标签' + item"
        >
          <view class="content-2">
            {{ '内容' + item }}
          </view>
        </van-tab>
      </van-tabs>
    </van-panel>

    <van-panel title="点击事件">
      <van-tabs @click="onClick">
        <van-tab
          v-for="item in [1,2]"
          :key="index"
          :title="'标签' + item"
        >
          <view class="content">
            {{ '内容' + item }}
          </view>
        </van-tab>
      </van-tabs>
    </van-panel>

    <van-panel title="粘性布局">
      <van-tabs sticky :scroll-top="scrollTop">
        <van-tab
          v-for="item in [1,2,3,4]"
          :key="index"
          :title="'标签' + item"
        >
          <view class="content">
            {{ '内容' + item }}
          </view>
        </van-tab>
      </van-tabs>
    </van-panel>

    <van-panel title="切换动画">
      <van-tabs animated>
        <van-tab
          v-for="item in [1,2,3,4]"
          :key="index"
          :title="'标签' + item"
        >
          <view class="content" style="height: 400px;">
            {{ '内容' + item }}
          </view>
        </van-tab>
      </van-tabs>
    </van-panel>

    <van-panel title="滑动切换">
      <van-tabs swipeable>
        <van-tab
          v-for="item in [1,2,3,4]"
          :key="index"
          :title="'标签' + item"
        >
          <view class="content">
            {{ '内容' + item }}
          </view>
        </van-tab>
      </van-tabs>
    </van-panel>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        tabs: [1, 2, 3, 4],
        tabsMore: [1, 2, 3, 4, 5, 6, 7, 8]

      }
    },
    methods: {
      onClickDisabled(event) {
        wx.showToast({
          title: `标签 ${event.mp.detail.index + 1} 已被禁用`,
          icon: 'none'
        });
      },

      onChange(event) {
        wx.showToast({
          title: `切换到标签 ${event.mp.detail.index + 1}`,
          icon: 'none'
        });
      },

      onClick(event) {
        wx.showToast({
          title: `点击标签 ${event.mp.detail.index + 1}`,
          icon: 'none'
        });
      },

      onPageScroll(event) {
        this.scrollTop = event.mp.scrollTop
      }
    }
  }
</script>
<style>
  .content {
    padding: 20px;
    background-color: #fff;
  }

  .content-2 {
    padding: 20px;
  }
</style>
