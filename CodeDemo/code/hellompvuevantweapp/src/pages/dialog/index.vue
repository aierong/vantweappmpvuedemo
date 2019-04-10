<template>
  <div>

    <van-panel title="消息提示" padding>
      <van-button
        plain
        type="primary"
        @click="onClickAlert"
      >
        消息提示
      </van-button>
      <van-button
        plain
        type="primary"
        @click="onClickAlert2"
      >
        无标题提示
      </van-button>
    </van-panel>


    <van-panel title="消息确认" padding>
      <van-button
        plain
        type="primary"
        @click="onClickConfirm"
      >
        消息确认
      </van-button>
    </van-panel>

    <van-panel title="组件调用" padding>
      <van-button
        plain
        type="danger"
        @click="showCustomDialog"
      >
        组件调用
      </van-button>
      <van-dialog
        use-slot
        async-close
        :show="show"
        show-cancel-button
        @close="onClose"
        confirm-button-open-type="getUserInfo"
        @getuserinfo="getUserInfo"
      >
        <van-field
          :value="username"
          label="用户名"
          placeholder="请输入用户名"
        />
        <van-field
          :value="password"
          type="password"
          label="密码"
          border="false"
          placeholder="请输入密码"
        />
      </van-dialog>
    </van-panel>

    <van-dialog id="van-dialog"/>

  </div>
</template>
<script>
  const message = '有赞是一家零售科技公司，致力于成为商家服务领域里最被信任的引领者';
  import Dialog from '../../../static/vant/dialog/dialog';

  export default {
    data() {
      return {
        show: false,
        username: '',
        password: ''
      }
    },
    methods: {
      showCustomDialog() {
        this.show = true
      },

      onClickAlert() {
        Dialog.alert({
          title: '标题',
          message
        });
      },

      getUserInfo(event) {
        console.log(event.mp.detail);
      },

      onClickAlert2() {
        Dialog.alert({
          message
        });
      },

      onClickConfirm() {
        Dialog.confirm({
          title: '标题',
          message
        });
      },

      onClose(event) {
        if (event.mp.detail === 'confirm') {
          setTimeout(() => {
            this.show = false
          }, 1000);
        } else {
          this.show = false
        }
      }
    }
  }
</script>
<style scoped>
</style>
