<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <!--
    change事件好像无法取到值,可以用input事件
    -->
    <van-datetime-picker type="datetime"
                         :value="currentDate"
                         :min-date="minDate"
                         :max-date="maxDate"
                         :show-toolbar="isshow"
                         @input="oninput1"
                         @change="onchange1"/>
    <mybr/>
    <mybr/>
    <!--
        confirm	点击完成按钮时触发的事件
        cancel	点击取消按钮时触发的事件
        -->
    <van-datetime-picker type="date"
                         :value="currentDate2"
                         :min-date="minDate"
                         @confirm="userselectdate"
                         @cancel="usercancel"
                         @input="oninput2"
                         @change="onchange2"/>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "datetimepicker" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        minHour : 10 ,
        maxHour : 20 ,
        minDate : new Date().getTime() ,
        maxDate : new Date( 2019 , 10 , 1 ).getTime() ,
        currentDate : new Date().getTime() ,

        currentDate2 : new Date().getTime() ,
        isshow : false
      }
    } ,
    //方法
    methods : {
      oninput1 ( event ) {
        //   //代码搞这里
        console.log( 'oninput1' , event )

        //console.log( event.mp.detail )

        const { detail , currentTarget } = event.mp;

        console.log( detail )
        console.log( currentTarget )

        const date = new Date( detail );

        console.log( date )
        console.log( date.toLocaleString() )
      } ,
      onchange1 ( event ) {
        // console.log( event )
        // console.log( event.mp.detail )
        // console.log( event.mp.detail.children )

      } ,
      oninput2 ( event ) {
        const { detail , currentTarget } = event.mp;

        console.log( detail )
        console.log( currentTarget )

        const date = new Date( detail );

        console.log( date )
        console.log( date.toLocaleDateString() )
      } ,
      onchange2 ( ev ) {
        //console.log( 'onchange2' , ev )

      } ,
      userselectdate ( event ) {
        console.log( 'onconfirm2' , event )

        const { detail , currentTarget } = event.mp;

        console.log( detail )
        console.log( currentTarget )

        const date = new Date( detail );

        console.log( date )
        console.log( date.toLocaleDateString() )

        wx.showToast( {
          title : date.toLocaleDateString() , //提示的内容,
          icon : 'success' , //图标,
          duration : 2000 , //延迟时间,
          mask : true , //显示透明蒙层，防止触摸穿透,
          success : res => {
            console.log( res )
          }
        } );
      } ,
      usercancel ( event ) {
        console.log( 'oncancel2' , event )
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
<style src="./datetimepicker.css"
       scoped>

</style>
