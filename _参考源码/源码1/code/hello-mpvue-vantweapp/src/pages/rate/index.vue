<template><div>
<van-panel title="基础用法">
  <van-rate
    custom-class="van-rate"
    data-key="value1"
    :value="value1"
  />
</van-panel>

<van-panel title="自定义图标">
  <van-rate
    custom-class="van-rate"
    icon="like"
    void-icon="like-o"
    data-key="value2"
    :value="value2"
  />
</van-panel>

<van-panel title="自定义样式">
  <van-rate
    custom-class="van-rate"
    data-key="value3"
    :value="value3"
    size="25"
    count="6"
    color="#07c160"
    void-color="#ceefe8"
    @change="onChange"
  />
</van-panel>

<van-panel title="禁用状态">
  <van-rate
    custom-class="van-rate"
    data-key="value4"
    :value="value4"
    disabled
  />
</van-panel>
</div></template>
<script>
  export default {
    data(){
      return{
        value1: 3,
        value2: 3,
        value3: 4,
        value4: 2
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
<style>
  .van-rate {
    margin-left: 15px;
  }

</style>
