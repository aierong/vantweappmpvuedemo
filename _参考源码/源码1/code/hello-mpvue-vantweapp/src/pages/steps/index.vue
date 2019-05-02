<template>
  <div>
    <van-panel title="基础用法">
      <van-steps
        :steps="steps"
        :active="active"
        custom-class="demo-margin-bottom"
      />
    </van-panel>

    <van-button custom-class="demo-margin-left" @click="nextStep">下一步</van-button>

    <van-panel title="竖向步骤条">
      <van-steps
        :steps="steps"
        :active="active"
        direction="vertical"
        active-color="#f44"
      />
    </van-panel>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        active: 0,
        steps: [
          {
            text: '步骤一',
            desc: '买家下单'
          },
          {
            text: '步骤二',
            desc: '商家接单'
          },
          {
            text: '步骤三',
            desc: '买家提货'
          },
          {
            text: '步骤四',
            desc: '交易完成'
          }
        ]
      }
    },
    methods: {
      nextStep() {
        this.active = ++(this.active) % 4
      }
    }
  }
</script>
