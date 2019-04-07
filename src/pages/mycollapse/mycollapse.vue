<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <van-collapse :value="activeNames"
                  @change="onChange">
      <van-collapse-item title="有赞微商城"
                         name="1">
        提供多样店铺模板，快速搭建网上商城
      </van-collapse-item>

      <van-collapse-item title="有赞零售"
                         name="2">
        网店吸粉获客、会员分层营销、一机多种收款，告别经营低效和客户流失
      </van-collapse-item>
      <van-collapse-item title="有赞美业"
                         name="3"
                         disabled>
        线上拓客，随时预约，贴心顺手的开单收银
      </van-collapse-item>
    </van-collapse>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  export default {
    name : "mycollapse" ,
    //数据模型
    data () {
      return {
        activeNames : [ "1" ]
      }
    } ,
    //方法
    methods : {
      onChange ( event ) {
        console.log( event )

        console.log( event.mp.detail )

        //由于不是:value="activeNames" 不是双向数据绑定 这里我们要主动赋值一下
        this.activeNames = event.mp.detail;
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
<style src="./mycollapse.css"
       scoped>

</style>
