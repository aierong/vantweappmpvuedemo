<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>

    <!--
    show-action	是否在搜索框右侧显示取消按钮
    -->
    <van-search :value="value1"
                placeholder="请输入搜索关键词"
                show-action
                @search="onSearch"
                @cancel="onCancel"/>

    <mybr/>
    <mybr/>
    <van-search :value="value2"
                placeholder="请输入搜索关键词"
                use-action-slot
                @change="onchange2"
                @search="onSearch2">
      <view slot="action"
            @tap="onSearch3">搜索
      </view>
    </van-search>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "search" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        value1 : '' ,
        value2 : ''
      }
    } ,
    //方法
    methods : {
      onSearch ( event ) {
        console.log( event )

        //要搜索的值
        let val = event.mp.detail;
        console.log( val )

        console.log( this.value1 )
        // 最好 把模型同步一下
        this.value1 = val;
      } ,
      //取消
      onCancel ( event ) {
        //这个参数好像没有啥用
        console.log( event )
      } ,
      onSearch2 ( event ) {
        console.log( event )

        let val = event.mp.detail;
        console.log( val )
        this.value2 = val;
      } ,
      onchange2 ( event ) {
        console.log( event )

        let val = event.mp.detail;
        console.log( val )

        // 最好 把模型同步一下
        this.value2 = val;
      } ,
      onSearch3 ( event ) {
        console.log( event )

        //要从模型this.value2中取值
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
<style src="./search.css">

</style>
