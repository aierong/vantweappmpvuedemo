<!--
作者:chenghao
功能:vue页
-->

 
<template>
  <!--
  特别提示:
  van-collapse组件的:value="activeNames"不是双向数据绑定, 所以我们需要在事件change中主动赋值一下,这样才会有效果
  -->
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

    <mybr/>
    <mybr/>
    <div>手风琴效果</div>
    <van-collapse :value="activeName2"
                  @change="onChange2"
                  accordion>
      <van-collapse-item title="有赞微商城"
                         name="1">
        提供多样店铺模板，快速搭建网上商城
      </van-collapse-item>
      <van-collapse-item title="有赞零售"
                         name="2">
        网店吸粉获客、会员分层营销、一机多种收款，告别经营低效和客户流失
      </van-collapse-item>
      <van-collapse-item title="有赞美业"
                         name="3">
        线上拓客，随时预约，贴心顺手的开单收银
      </van-collapse-item>
    </van-collapse>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "mycollapse" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        //普通版本是数组
        activeNames : [ "1" ] ,
        //手风琴的是一个值
        activeName2 : '1'
      }
    } ,
    //方法
    methods : {
      onChange ( event ) {
        console.log( event )

        console.log( event.mp.detail )

        //由于 :value="activeNames" 不是双向数据绑定 这里我们要主动赋值一下
        this.activeNames = event.mp.detail;
      } ,
      onChange2 ( event ) {
        console.log( event )

        //由于 :value="activeName2" 不是双向数据绑定 这里我们要主动赋值一下
        this.activeName2 = event.mp.detail;
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
