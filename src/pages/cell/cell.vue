<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <van-cell title="标题"
              icon="location-o"
              @click="onclick"
              value="内容"
              is-link/>
    <mybr/>
    <mybr/>
    <div>单击事件,还可以取到其他参数</div>
    <van-cell title="标题"
              icon="location-o"
              @click="onclick2"
              value="内容"
              clickable
              :data-name="mydata"
              is-link/>
    <mybr/>
    <mybr/>
    <van-cell value="内容"
              icon="shop-o"
              is-link>
      <view slot="title">
        <!--        <view class="van-cell-text">单元格</view>-->
        <span>单元格</span>
        <van-tag round
                 plain
                 type="danger">9
        </van-tag>
      </view>
    </van-cell>
    <mybr/>
    <mybr/>
    <van-cell title="单元格">
      <van-icon slot="right-icon"
                name="search"
                class="van-cell__right-icon"/>
    </van-cell>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "cell" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        msg : '' ,
        mydata : 'qq'
      }
    } ,
    //方法
    methods : {
      onclick () {
        //代码搞这里
        console.log( 'dj' )
      } ,
      onclick2 ( ee ) {
        // ee.mp.currentTarget.dataset.name 可以取到  van-cell 中设置的 data-name=""
        let val = ee.mp.currentTarget.dataset.name;
        console.log( val )
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
       src="./cell.css">
  .custom-text {
    margin-right: 5px;
    vertical-align: middle;
  }
</style>
