<template>
  <div>
<van-panel title="基本用法">
  <van-search
    :value="value"
    placeholder="请输入搜索关键词"
    @change="onChange"
    @search="onSearch"
  />
</van-panel>

<van-panel title="监听对应事件">
  <van-search
    :value="value"
    show-action
    placeholder="请输入搜索关键词"
    @change="onChange"
    @search="onSearch"
    @cancel="onCancel"
    @clear="onClear"
  />
</van-panel>

<van-panel title="自定义行动按钮">
  <van-search
    :value="value"
    placeholder="请输入搜索关键词"
    use-action-slot
    @change="onChange"
    @search="onSearch"
  >
    <view slot="action" @tap="onSearch">搜索</view>
  </van-search>
</van-panel>
</div>
</template>

<script>
export default {
  data(){
    return{
      value: ''
    }
  },
  methods:{
    onChange(e) {
      this.value=e.mp.detail
    },

    onSearch(event) {
      if (this.value) {
        wx.showToast({title: '搜索：' + this.value,icon: 'none'});
      }
    },
    onCancel() {
      wx.showToast({title: '取消',icon: 'none'});
    },
    onClear() {
      wx.showToast({title: '清空',icon: 'none' });
    }
  }
}
</script>

<style>

</style>
