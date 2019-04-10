<template>
  <div>
    <van-panel title="文字提示" padding>
      <van-button @tap="showToast" class="demo-margin-right">文字提示</van-button>
      <van-button @tap="showLongToast">长文字提示</van-button>
    </van-panel>

    <van-panel title="加载提示" padding>
      <van-button @tap="showLoadingToast">加载提示</van-button>
    </van-panel>

    <van-panel title="成功/失败提示" padding>
      <van-button @tap="showSuccessToast" class="demo-margin-right">成功提示</van-button>
      <van-button @tap="showFailToast">失败提示</van-button>
    </van-panel>

    <van-panel title="高级用法" padding>
      <van-button @tap="showCustomizedToast">高级用法</van-button>
    </van-panel>

    <van-toast id="van-toast"/>
  </div>
</template>
<script>
  import Toast from '../../../static/vant/toast/toast';

  export default {
    data() {
      return {}
    },
    methods: {
      showToast() {Toast('提示内容');},
      showLongToast() {
        Toast('这是一条长文字提示，超过一定字数就会换行');
      },

      showLoadingToast() {
        Toast.loading({ mask: true, message: '加载中...' });
      },

      showSuccessToast() {
        Toast.success('成功文案');
      },

      showFailToast() {
        Toast.fail('失败提示');
      },

      showCustomizedToast(duration) {
        const text = second => `倒计时 ${second} 秒`;
        const toast = Toast.loading({
          duration: 0,
          forbidClick: true,
          loadingType: 'spinner',
          message: text(3)
        });

        let second = 3;
        const timer = setInterval(() => {
          second--;
          if (second) {
            toast.setData({ message: text(second) });
          } else {
            clearInterval(timer);
            Toast.clear();
          }
        }, 1000);
      }
    }
  }
</script>
<style>

</style>
