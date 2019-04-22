<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <mybr/>
    <mybr/>
    <van-button @click="showToast"
                class="demo-margin-right">文字提示
    </van-button>

    <van-button @click="showLongToast">长文字提示</van-button>
    <mybr/>
    <mybr/>
    <van-button @click="showLoadingToast">加载提示</van-button>
    <mybr/>
    <mybr/>
    <van-button @click="showSuccessToast">成功提示</van-button>
    <van-button @click="showFailToast">失败提示</van-button>
    <mybr/>
    <mybr/>
    <van-button @click="showCustomizedToast">高级用法</van-button>
    <!--
    注意要配一个van-toast,才会显示提示 ,默认id van-toast

    -->
    <van-toast id="van-toast"/>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  // 配置文件json也要配置,这里代码也要引用
  // 代码中也要引用
  // 注意引用路径
  import Toast from '../../../static/vant/toast/toast';

  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "mytoast" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        msg : ''
      }
    } ,
    //方法
    methods : {
      showToast () {
        Toast( '提示内容' );
      } ,
      showLongToast () {
        Toast( '这是一条长文字提示，超过一定字数就会换行' );
      } ,
      showLoadingToast () {
        //3000 会自动关闭
        Toast.loading( {
          mask : true ,
          message : '加载中...'
        } );
      } ,
      showSuccessToast () {
        Toast.success( '成功文案' );
      } ,
      showFailToast () {
        Toast.fail( '失败提示' );
      } ,
      showCustomizedToast () {
        //高级用法
        const text = second => `倒计时 ${ second } 秒`;
        const toast = Toast.loading( {
          duration : 0 ,
          forbidClick : true ,
          loadingType : 'spinner' ,
          message : text( 3 )
        } );

        let second = 3;

        const timer = setInterval( () => {
          second--;
          if ( second ) {
            toast.setData( { message : text( second ) } );
          }
          else {
            clearInterval( timer );
            //关闭提示
            Toast.clear();
          }
        } , 1000 );
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
<style src="./mytoast.css"
       scoped>

</style>
