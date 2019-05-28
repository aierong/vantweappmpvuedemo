<!--
作者:chenghao
Date: 2019/5/28
Time: 16:33
功能:
-->

<!-- html代码片段 -->
<template>

  <div>
    <button @click="sm">扫描条码</button>
    <mybr/>
    <mybr/>
    <div>{{ '扫描结果:' + bar1 }}</div>
    <div>{{ '条码类型:' + bartype1 }}</div>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "scanbarcode" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        bar1 : '' ,
        bartype1 : ''
      }
    } ,
    //方法
    methods : {
      sm () {
        //console.log( 'sm' )

        wx.scanCode( {
          success : ( res ) => {
            // res 返回这样格式的值
            // {errMsg: "scanCode:ok", result: "AJ1905280651", scanType: "CODE_128", charSet: "UTF-8", rawData: "QUoxOTA1MjgwNjUx"}
            // {errMsg: "scanCode:ok", result: "11二维码test", scanType: "QR_CODE", charSet: "UTF-8", rawData: "MTHkuoznu7TnoIF0ZXN0"}

            console.log( res )

            //条码值
            this.bar1 = res.result;
            //条码类型
            this.bartype1 = res.scanType;
          } ,
          fail : ( err ) => {
            console.log( err )
          }
        } )
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
       src="./scanbarcode.css">
</style>
