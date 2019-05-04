<!--
作者:chenghao
Date: 2019/5/4
Time: 19:50
功能:
-->

<!-- html代码片段 -->
<template>

  <div>
    <view>基础使用</view>
    <van-rate :value="val1"
              @change="onChange1"/>
    <mybr/>
    <mybr/>
    <mybr/>
    <mybr/>
    <view>自己定义图标</view>
    <!--
    icon	选中时的图标名称或图片链接，可选值见 Icon 组件
    void-icon	未选中时的图标名称或图片链接

    color	选中时的颜色
    void-color	未选中时的颜色

    size	图标大小 (px)      默认值：20
     -->

    <van-rate :value="val2"
              icon="like"
              void-icon="like-o"
              color="#f44"
              void-color="#eee"
              size="38"
              @change="onChange2"
    />
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "rate" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        val1 : 3 ,
        val2 : 1
      }
    } ,
    //方法
    methods : {
      onChange1 ( event ) {
        //代码搞这里
        console.log( event )

        this.val1 = event.mp.detail
      } ,
      onChange2 ( event ) {
        console.log( event )

        this.val2 = event.mp.detail
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
<style src="./rate.css"
       scoped>
</style>
