<template><div>
<van-panel title="基础用法">
  <van-cell-group>
    <van-field :value="value" placeholder="请输入用户名" border="false" clearable />
  </van-cell-group>
</van-panel>

<van-panel title="自定义类型">
  <van-cell-group>
    <van-field
      :value="username"
      label="用户名"
      placeholder="请输入用户名"
      clearable
      icon="question-o"
      icon-class="icon"
      required
      @click-icon="onClickIcon"
    />
    <van-field
      :value="password"
      type="password"
      label="密码"
      placeholder="请输入密码"
      required
      border="false"
    />
  </van-cell-group>
</van-panel>

  <van-panel title="禁用输入框">
    <van-cell-group>
      <van-field value="输入框已禁用" label="用户名" left-icon="contact" disabled border="false"/>
    </van-cell-group>
  </van-panel>

<van-panel title="错误提示">
  <van-cell-group>
    <van-field :value="username2" label="用户名" placeholder="请输入用户名" error/>
    <van-field :value="phone" label="手机号" placeholder="请输入手机号" error-message="手机号格式错误" border="false"/>
  </van-cell-group>
</van-panel>

<van-panel title="高度自适应">
  <van-cell-group>
    <van-field
      :value="message"
      label="留言"
      type="textarea"
      placeholder="请输入留言"
      rows="1"
      autosize
      border="false"
    />
  </van-cell-group>
</van-panel>

<van-panel title="插入按钮">
  <van-cell-group>
    <van-field
      :value="sms"
      center
      clearable
      label="短信验证码"
      placeholder="请输入短信验证码"
      use-button-slot
      border="false"
      @change="onFieldChange"
      @blur="onFieldBlur"
    >
      <van-button slot="button" size="small" type="primary" custom-class="button" @tap="onSendSms">发送验证码</van-button>
    </van-field>
  </van-cell-group>
</van-panel>
</div></template>
<script>
  export default {
    data(){
      return{
        sms: '',
        value: '',
        password: '',
        username: '',
        username2: '',
        message: '',
        phone: '1365577'
      }
    },
    methods:{
      onClickIcon() {
        wx.showToast({icon: 'none',title: '点击图标'});
      },

      onFieldChange({ detail }) {
        console.log('change', detail);
        this.sms=detail;
      },

      onFieldBlur({ detail }) {
        console.log('blur', detail);
      },

      onSendSms() {
        console.log('onSendSms', this.sms);
      }

    }
  }
</script>
<style>
  .button {
    vertical-align: middle;
  }

  .icon {
    color: #1989fa;
  }

</style>
