<template>
  <div>
    <van-panel title="马克思主义哲学最基础的部分是（　　　）。" padding>
      <van-radio-group
        :value="radio1"
        data-key="radio1"
        custom-class="demo-radio-group"
        @change="onChange"
      >
        <van-radio name="1" custom-class="demo-radio">A.唯物主义</van-radio>
        <van-radio name="2" custom-class="demo-radio">B.辩证法</van-radio>
        <van-radio name="3" custom-class="demo-radio">C.科学社会主义</van-radio>
        <van-radio name="4" custom-class="demo-radio">D.历史唯物主义</van-radio>
      </van-radio-group>
    </van-panel>

    <van-panel title="禁用状态" padding>
      <van-radio-group
        disabled
        :value="radio2"
        data-key="radio2"
        custom-class="demo-radio-group"
        @change="onChange"
      >
        <van-radio name="1" custom-class="demo-radio">单选框 1</van-radio>
        <van-radio name="2" custom-class="demo-radio">单选框 2</van-radio>
      </van-radio-group>
    </van-panel>

    <van-panel title="自定义颜色" padding>
      <van-radio
        name="1"
        value="1"
        custom-class="demo-radio"
        checked-color="#07c160"
      >
        单选框
      </van-radio>
    </van-panel>

    <van-panel title="与 Cell 组件一起使用">
      <van-radio-group :value="radio3">
        <van-cell-group>
          <van-cell title="单选框 1" clickable data-value="1" @click="onClick">
            <van-radio name="1">单选框 1</van-radio>
          </van-cell>
          <van-cell title="单选框 2" clickable data-value="2" @click="onClick">
            <van-radio name="2">单选框 2</van-radio>
          </van-cell>
        </van-cell-group>
      </van-radio-group>
    </van-panel>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        radio1: '1',
        radio2: '2',
        radio3: '1'
      }
    },
    methods: {
      onChange(event) {
        console.log("event.mp: ",event.mp)
        const {key} = event.mp.currentTarget.dataset;
        this[key] = event.mp.detail;
      },
      onClick(event) {
        const {value} = event.mp.currentTarget.dataset;
        this.radio3 = value
      }
    }
  }
</script>
<style>
  .demo-radio-group {
    padding: 0 17px;
  }
  .demo-radio {
    margin-bottom: 10px;
  }
</style>
