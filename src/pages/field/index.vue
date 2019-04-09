<!--
作者:chenghao
功能:vue页
-->

<!--
 特别提示:
 需要注册change事件,实现双向数据绑定
-->
<template>

  <div>
    <van-panel title="基础用法">
      <van-field :value="value1"
                 @change="onChange1"
                 placeholder="请输入用户名"/>
      <button @click="dj">得值</button>
    </van-panel>
    <mybr/>
    <mybr/>
    <van-panel title="自定义类型">
      <!--
      注册了click-icon事件,好像没有反应
      -->
      <van-field :value="username"
                 label="用户名"
                 placeholder="请输入用户名"
                 clearable
                 icon="question-o"
                 icon-class="icon"
                 required
                 @click-icon="onClickIcon"/>
      <van-field :value="password"
                 type="password"
                 label="密码"
                 placeholder="请输入密码"
                 required
                 border="false"/>

    </van-panel>
    <mybr/>
    <mybr/>
    <van-panel title="插入按钮">
      <van-field :value="sms"
                 center
                 clearable
                 label="短信验证码"
                 placeholder="请输入短信验证码"
                 use-button-slot
                 border="false"
                 @change="onFieldChange">
        <van-button slot="button"
                    size="small"
                    type="primary"
                    @tap="onSendSms">发送验证码
        </van-button>
      </van-field>

    </van-panel>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "index" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        value1 : '' ,
        password : '' ,
        username : '' ,
        sms : ''
      }
    } ,
    //方法
    methods : {
      dj () {
        //代码搞这里
        console.log( this.value1 )
      } ,
      onChange1 ( event ) {
        this.value1 = event.mp.detail
      } ,
      onFieldBlur ( event ) {
        console.log( event )

        console.log( 'blur' , event.mp.detail.value );
      } ,
      onFieldChange ( event ) {
        console.log( 'change' , event.mp.detail );

        this.sms = event.mp.detail;
      } ,
      onSendSms () {
        console.log( this.sms )
      } ,
      onClickIcon () {
        console.log( 'q1' )

        wx.showToast( {
          title : 'q' , //提示的内容,
          icon : 'success' , //图标,
          duration : 2000 , //延迟时间,
          mask : true , //显示透明蒙层，防止触摸穿透,
          success : res => {
            console.log( res )
          }
        } );
      } ,
    } ,
    //计算属性
    computed : {
      //name() {
      //代码搞这里
      //return this.data;
      //}
    } ,
    //生命周期(mounted)
    mounted () {

    } ,
  }
</script>

<!-- 样式代码片段  scoped -->
<style src="./index.css"
       scoped>

</style>
