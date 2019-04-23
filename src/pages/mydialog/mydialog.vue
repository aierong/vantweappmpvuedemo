<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <mybr/>
    <mybr/>
    <van-button plain
                type="primary"
                @click="onClickAlert">消息提示
    </van-button>
    <mybr/>
    <van-button plain
                type="primary"
                @click="onClickAlert2">
      无标题提示
    </van-button>
    <mybr/>
    <van-button plain
                type="primary"
                @click="onClickConfirm">
      消息确认
    </van-button>
    <mybr/>
    <van-button plain
                type="danger"
                @click="showCustomDialog">
      组件调用
    </van-button>
    <!--
    use-slot	是否使用自定义内容的插槽
    close 关闭弹窗
    -->
    <van-dialog use-slot
                :show="show"
                show-cancel-button
                @close="onClose">
      <van-field :value="username"
                 label="用户名"
                 placeholder="请输入用户名"/>
      <van-field :value="password"
                 type="password"
                 label="密码"
                 border="false"
                 placeholder="请输入密码"/>
    </van-dialog>
    <!--
    注意要配一个van-dialog,才会显示提示 ,默认id van-dialog
    -->
    <van-dialog id="van-dialog"/>

  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  // 配置文件json也要配置,这里代码也要引用
  // 代码中也要引用
  // 注意引用路径
  import Dialog from '../../../static/vant/dialog/dialog';

  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "mydialog" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        show : false ,
      }
    } ,
    //方法
    methods : {

      onClickAlert () {
        const message = '有赞是一家零售科技公司，致力于成为商家服务领域里最被信任的引领者';

        Dialog.alert( {
          title : '标题' ,
          message
        } );
      } ,
      onClickAlert2 () {
        const message = '有赞是一家零售科技公司，致力于成为商家服务领域里最被信任的引领者';

        Dialog.alert( {
          message
        } );
      } ,
      onClickConfirm () {
        const message = '有赞是一家零售科技公司,你确定加入吗?';

        Dialog.confirm( {
          title : '标题' ,
          message
        } ).then( () => {
          // on confirm
          console.log( '提交' )
        } ).catch( () => {
          // on cancel
          console.log( '取消' )
        } );
      } ,
      showCustomDialog () {
        //把显示开关打开
        this.show = true
      } ,
      //close 关闭弹窗
      onClose ( event ) {
        console.log( event.mp.detail )

        if ( event.mp.detail === 'confirm' ) {
          //点击了 确定按钮
          console.log( '点击确定' )
        }
        else {
          //点击了 取消按钮
          console.log( '点击取消' )
        }

        this.show = false
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
<style scoped
       src="./mydialog.css">

</style>
