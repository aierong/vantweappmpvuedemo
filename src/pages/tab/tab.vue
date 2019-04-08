<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>
  <!--
  特别提示:
  van-tabs组件的:active="active"不是双向数据绑定,
  所以tab切换后active值已经不是最新的啦!如果需要保持最新,需要在事件change中主动赋值一下

  collapse也有类似情况
  -->
  <div>
    <van-tabs :active="active1"
              @change="onChange1">
      <van-tab title="标签 1">内容 1</van-tab>
      <van-tab title="标签 2">内容 2</van-tab>
      <van-tab title="标签 3">内容 3</van-tab>
      <van-tab title="标签 4">内容 4</van-tab>
    </van-tabs>
    <mybr/>
    <mybr/>
    <!--
    多于 4 个标签时，Tab可横向滚动
    -->
    <div>Tab可横向滚动</div>
    <van-tabs @change="onChange2"
              :active="active2">
      <van-tab title="标签1">内容 1</van-tab>
      <van-tab title="标签2">内容 2</van-tab>
      <van-tab title="标签3">内容 3</van-tab>
      <van-tab title="标签4">内容 4</van-tab>
      <van-tab title="标签5">内容 5</van-tab>
      <van-tab title="标签6">内容 6</van-tab>
      <van-tab title="标签7">内容7</van-tab>
      <van-tab title="标签8">内容8</van-tab>
      <van-tab title="标签9">内容9</van-tab>
      <van-tab title="标签10">内容10</van-tab>
      <van-tab title="标签11">内容11</van-tab>
    </van-tabs>

    <mybr/>
    <mybr/>
    <!--
    disabled 点击被禁用的标签时触发
    -->
    <div>禁用tab，并且响应事件</div>
    <van-tabs @change="onChange3"
              @disabled="onClickDisabled"
              :active="active3">
      <van-tab title="标签 1">内容 1</van-tab>
      <van-tab title="标签 2"
               disabled>内容 2
      </van-tab>
      <van-tab title="标签 3">内容 3</van-tab>
    </van-tabs>
    <mybr/>
    <mybr/>
    <div>tab单击</div>
    <!--
    单击事件中好像取不到索引和标题,建议还是使用change
    -->
    <van-tabs @click="onClick4"
              @change="onChange4"
              :active="active4">
      <van-tab title="标签 1">内容 1</van-tab>
      <van-tab title="标签 2">内容 2</van-tab>
    </van-tabs>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "tab" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        //从0开始的
        active1 : 2 ,

        active2 : 0 ,

        active3 : 0 ,

        active4 : 1
      }
    } ,
    //方法
    methods : {
      onChange1 ( event ) {
        //代码搞这里
        console.log( event )

        //选择的索引
        console.log( event.mp.detail.index )
        //标题
        console.log( event.mp.detail.title )

        console.log( this.active1 )
        //最好手动赋值一下,要不值不是最新的
        this.active1 = event.mp.detail.index;

        console.log( this.active1 )
      } ,
      onChange2 ( event ) {
        //最好手动赋值一下,要不值不是最新的
        this.active2 = event.mp.detail.index;

        console.log( this.active2 )
      } ,
      onChange3 ( event ) {
        //最好手动赋值一下,要不值不是最新的
        this.active3 = event.mp.detail.index;

        console.log( this.active3 )
      } ,
      onClickDisabled ( event ) {
        //选择的索引
        console.log( event.mp.detail.index )
        //标题
        console.log( event.mp.detail.title )
      } ,
      onClick4 ( event ) {
        console.log( event )

        //单击事件中好像取不到索引和标题,建议还是使用change

        // //选择的索引
        // console.log( event.mp.detail.index )
        // //标题
        // console.log( event.mp.detail.title )

        // console.log( this.active4 )
      } ,
      onChange4 ( event ) {
        //代码搞这里
        console.log( event )

        //选择的索引
        console.log( event.mp.detail.index )

        //最好手动赋值一下,要不值不是最新的
        this.active4 = event.mp.detail.index;

        console.log( this.active4 )
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
       src="./tab.css">

</style>
