<!--
作者:chenghao
功能:vue页
-->

<!--
 特别提示:
 需要注册change事件,实现双向数据绑定
-->
<template>

  <div>
    <div>基础使用</div>
    <!--    通过value绑定值当前选中项的 name-->
    <van-radio-group :value="radio1"
                     @change="onChange1">
      <van-radio name="1">单选框 1</van-radio>
      <van-radio name="2">单选框 2</van-radio>
    </van-radio-group>
    <mybr/>
    <mybr/>
    <div>与 Cell 组件一起使用</div>
    <van-radio-group :value="radio2"
                     @change="onChange2">
      <van-cell-group>
        <van-cell title="单选框 1"
                  clickable
                  data-name="v1"
                  @click="onClick">
          <van-radio name="v1"/>
        </van-cell>
        <van-cell title="单选框 2"
                  clickable
                  data-name="v2"
                  @click="onClick">
          <van-radio name="v2"/>
        </van-cell>
      </van-cell-group>
    </van-radio-group>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "radios" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        radio1 : '1' ,
        radio2 : 'v2'
      }
    } ,
    //方法
    methods : {
      onChange1 ( ev ) {
        //代码搞这里
        console.log( ev )

        this.radio1 = ev.mp.detail;
      } ,
      onChange2 ( ev ) {
        //代码搞这里
        console.log( ev )

        this.radio2 = ev.mp.detail;
      } ,
      onClick ( ee ) {
        console.log( ee )

        console.log( ee.mp.currentTarget )
        console.log( ee.mp.currentTarget.dataset )
        console.log( ee.mp.currentTarget.dataset.name )

        // ee.mp.currentTarget.dataset.name 可以取到  van-cell 中设置的 data-name="v2"
        this.radio2 = ee.mp.currentTarget.dataset.name;
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
<style src="./radios.css">

</style>
