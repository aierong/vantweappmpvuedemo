<template>
  <div>
    <van-tabs  :active="active">
      <van-tab title="基础用法">
        <van-cell-group>
          <van-cell title="单元格" value="内容"/>
          <van-cell title="单元格"  value="内容"  label="描述信息描述信息描述信息描述信息描述信息描述信息" :border="false"/>
        </van-cell-group>
      </van-tab>
      <van-tab title="单元格大小">
        <van-cell-group>
          <van-cell title="单元格" value="内容" size="large"/>
          <van-cell title="单元格" value="内容" label="描述信息" size="large" :border="false"/>
        </van-cell-group>
      </van-tab>
      <van-tab title="展示图标">
        <van-cell title="单元格" icon="location-o" :border="false"/>
      </van-tab>
      <van-tab title="展示箭头">
        <van-cell title="单元格" is-link/>
        <van-cell title="单元格" value="内容" is-link/>
        <van-cell  title="单元格" is-link arrow-direction="down" value="内容" :border="false" url="/pages/index/index"/>
      </van-tab>
      <van-tab title="高级用法">
        <van-cell value="内容" icon="shop-o" is-link>
          <view slot="title">
            <view class="title">单元格</view>
            <van-tag type="danger">标签</van-tag>
          </view>
        </van-cell>
        <van-cell title="单元格" icon="location-o" is-link/>
        <van-cell title="单元格" :border="false">
          <van-icon slot="right-icon" name="search"/>
        </van-cell>
      </van-tab>
    </van-tabs>
  </div>
</template>
<script>

  export default {
    components: {

    },
    data(){
      return {
        active:0
      }
    }
  }
</script>
<style scoped>
  .title {
    margin-right: 5px;
    display: inline-block;
    vertical-align: middle;
  }
</style>
