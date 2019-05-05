<!--
作者:chenghao
Date: 2019/5/5
Time: 9:30
功能:
-->

<!-- html代码片段 -->
<template>

  <div>
    <view>基本使用</view>
    <van-slider value="50"
                @change="onChange1"/>
    <mybr/>
    <mybr/>
    <view>最大，最小,步长</view>
    <van-slider min="10"
                max="90"
                :value="v2"
                step="5"
                @change="onChange2"/>
    <mybr/>
    <mybr/>
    <view>自定义</view>
    <!--
    bar-height	进度条高度
    -->
    <van-slider :value="currentValue"
                custom-class="slider"
                use-button-slot
                active-color="#f44"
                bar-height="4px"
                @drag="onDrag">
      <view class="custom-button"
            slot="button">
        {{ currentValue }}
      </view>
    </van-slider>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "myslider" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        v2 : 50 ,
        currentValue : 50
      }
    } ,
    //方法
    methods : {
      onChange1 ( event ) {
        //取到值
        let val = event.mp.detail;

        console.log( val )

      } ,
      onChange2 ( event ) {
        //取到值
        let val = event.mp.detail;

        console.log( val )

        this.v2 = val;
      } ,
      onDrag ( event ) {
        //value属性中取到值
        let val = event.mp.detail.value;

        console.log( val )

        this.currentValue = val;
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
<style src="./myslider.css"
       scoped>
</style>
