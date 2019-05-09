<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <view>按钮类型</view>
    <van-button type="default">默认按钮</van-button>


    <van-button type="primary">主要按钮</van-button>

    <van-button type="info">信息按钮</van-button>

    <van-button type="warning">警告按钮</van-button>

    <van-button @click="dj"
                type="danger">危险按钮
    </van-button>
    <mybr/>
    <view>朴素按钮</view>
    <van-button plain
                type="primary">朴素按钮
    </van-button>
    <van-button plain
                type="danger">朴素按钮
    </van-button>
    <mybr/>
    <view>细边框</view>
    <van-button plain
                hairline
                type="primary">细边框按钮
    </van-button>
    <van-button plain
                hairline
                type="danger">细边框按钮
    </van-button>
    <mybr/>
    <view>禁用按钮</view>
    <van-button disabled
                type="primary">禁用状态
    </van-button>
    <van-button disabled
                type="danger">禁用状态
    </van-button>
    <mybr/>
    <view>加载状态</view>
    <van-button loading
                type="primary"/>
    <van-button loading
                type="danger"
                loading-text="加载中..."/>
    <mybr/>
    <view>按钮形状</view>
    <van-button square
                type="primary">方形按钮
    </van-button>
    <van-button round
                type="danger">圆形按钮
    </van-button>
    <mybr/>
    <view>按钮尺寸</view>
    <van-button size="large">大号按钮</van-button>
    <van-button size="normal">普通按钮</van-button>
    <van-button size="small">小型按钮</van-button>
    <van-button size="mini">迷你按钮</van-button>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "button" ,
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
      dj () {
        console.log( 'dj' )
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
       src="./button.css">

</style>
