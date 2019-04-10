<template>
  <div>
    <van-panel title="Circular" padding>
      <van-loading custom-class="loading"/>
      <van-loading custom-class="loading shadow" color="#fff"/>
    </van-panel>

    <van-panel title="Spinner" padding>
      <van-loading custom-class="loading" type="spinner"/>
      <van-loading custom-class="loading shadow" type="spinner" color="#fff"/>
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
  .loading {
    margin-right: 20px;
  }

  .shadow {
    padding: 10px;
    border-radius: 3px;
    background-color: rgba(0, 0, 0, .5);
  }
</style>
