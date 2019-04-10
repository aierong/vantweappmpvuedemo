<template>
  <div>
  <div title="基础用法">
    <van-row>
      <van-col span="8">span: 8</van-col>
      <van-col span="8">span: 8</van-col>
      <van-col span="8">span: 8</van-col>
    </van-row>

    <van-row>
      <van-col span="4">span: 4</van-col>
      <van-col span="10" offset="4">offset: 4, span: 10</van-col>
    </van-row>

    <van-row>
      <van-col offset="12" span="12">offset: 12, span: 12</van-col>
    </van-row>
  </div>
  <div title="在列元素间增加间距">
    <van-row gutter="20">
      <van-col span="8">span: 8</van-col>
      <van-col span="8">span: 8</van-col>
      <van-col span="8">span: 8</van-col>
    </van-row>
  </div>
  </div>
</template>
<script>
  export default {

  }
</script>
<style scoped>
  .title {
    margin-right: 5px;
    display: inline-block;
    vertical-align: middle;
  }
</style>
