<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <van-panel title="标题"
               desc="描述信息"
               status="状态a">
      <view>内容</view>
    </van-panel>
    <mybr/>
    <mybr/>

    <van-panel title="标题"
               desc="描述信息"
               status="状态2"
               use-footer-slot>
      <view>内容</view>
      <!--
      加个样式把按钮搞右边去
      -->
      <view style="text-align: right;"
            slot="footer">
        <van-button size="small">按钮</van-button>
        <van-button size="small"
                    type="danger">按钮
        </van-button>
      </view>
    </van-panel>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "mypanel" ,
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
      //methodsname() {
      //代码搞这里
      //},

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
<style src="./mypanel.css"
       scoped>

</style>
