<!--
作者:chenghao
Date: 2019/5/5
Time: 21:17
功能:
-->

<!-- html代码片段 -->
<template>

  <div>
    <view>基础使用</view>
    <van-picker value-key="txt"
                :columns="columnsobj1"
                @change="onChange1"/>

    <mybr/>
    <mybr/>
    <mybr/>
    <mybr/>
    <view>给默认值</view>
    <van-picker value-key="txt"
                :columns="colobjlist"
                @change="onChange2"/>

  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "pickerobj" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        columnsobj1 : [
          {
            txt : "杭州" ,

            ids : 1 ,
            nos : "a"
          } ,
          {
            txt : "宁波" ,

            ids : 2 ,
            nos : "b"
          } ,
          {
            txt : "温州" ,

            ids : 3 ,
            nos : "c"
          }
        ] ,

        colobjlist : [
          {
            values : [
              {
                txt : "杭州" ,

                ids : 11 ,
                nos : "a1"
              } ,
              {
                txt : "宁波" ,

                ids : 22 ,
                nos : "b2"
              } ,
              {
                txt : "温州" ,

                ids : 33 ,
                nos : "c3"
              }
            ] ,
            defaultIndex : 2
          }
        ] ,
      }
    } ,
    //方法
    methods : {
      onChange1 ( event ) {
        console.log( event )

        let obj = event.mp.detail;
        console.log( obj )

        //得到索引
        let index = obj.index;

        //得到值，是一个对象
        let val = obj.value;

        // {txt: "宁波", ids: 2, nos: "b"}
        console.log( val.txt )
        console.log( val.ids )
        console.log( val.nos )
      } ,
      onChange2 ( event ) {
        console.log( event )

        let obj = event.mp.detail;
        console.log( obj )

        //得到索引
        let index = obj.index;

        //得到值，是一个数组，取第一个对象
        let val = obj.value[ 0 ];

        // {txt: "宁波", ids: 2, nos: "b"}
        console.log( val.txt )
        console.log( val.ids )
        console.log( val.nos )
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
<style src="./pickerobj.css"
       scoped>
</style>
