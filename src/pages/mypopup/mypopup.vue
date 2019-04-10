<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <van-popup :show="show1"
               @close="onClose1">内容
    </van-popup>
    <van-button @click="dj1"
                size="small">弹出popup
    </van-button>
    <mybr/>
    <van-popup :show="show2"
               position="top"
               @close="onClose2">
      <div> 内容
      </div>
      <div> 内容2
      </div>
    </van-popup>
    <van-button @click="dj2"
                size="small">顶部弹出popup
    </van-button>
    <mybr/>
    <van-popup :show="show3"
               position="bottom">
      <!--      <div>选择</div>-->
      <van-datetime-picker type="date"
                           :value="currentDate3"
                           :min-date="minDate3"
                           @confirm="onconfirm3"
                           @cancel="oncancel3"/>
    </van-popup>
    <van-button @click="dj3"
                size="small">弹出popup选择日期
    </van-button>
    <mybr/>

    <van-button @click="toggleRightPopup">右侧弹出</van-button>
    <van-popup :show="show.right"
               position="right"
               custom-class="right"
               @close="toggleRightPopup">
      <van-button @click="toggleRightPopup">关闭弹层
      </van-button>

      <van-button @click="toggleRightPopup2">右侧弹出</van-button>
      <van-popup :show="show.right2"
                 position="right"
                 custom-class="right"
                 @close="toggleRightPopup2">
        <van-button @click="toggleRightPopup2">关闭弹层</van-button>
      </van-popup>
    </van-popup>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "mypopup" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        show1 : false ,
        show2 : false ,
        show3 : false ,

        currentDate3 : new Date().getTime() ,
        minDate3 : new Date().getTime() ,

        show : {

          right : false ,
          right2 : false
        } ,
      }
    } ,
    //方法
    methods : {
      dj1 () {

        this.show1 = true;
      } ,
      onClose1 () {
        this.show1 = false;
      } ,
      dj2 () {
        this.show2 = true;
      } ,
      onClose2 () {
        this.show2 = false;
      } ,
      dj3 () {
        this.show3 = true;
      } ,
      // onClose3 () {
      //
      // } ,
      onconfirm3 ( event ) {
        //console.log( 'onconfirm2' , event )

        const { detail , currentTarget } = event.mp;

        // console.log( detail )
        // console.log( currentTarget )

        const date = new Date( detail );

        console.log( date )
        console.log( date.toLocaleDateString() )

        this.show3 = false;
      } ,
      oncancel3 ( event ) {
        this.show3 = false;
      } ,
      toggleRightPopup () {
        this.show.right = !this.show.right
      } ,
      toggleRightPopup2 () {
        this.show.right2 = !this.show.right2
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
<style src="./mypopup.css">

</style>
