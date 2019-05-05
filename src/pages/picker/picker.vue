<!--
作者:chenghao
Date: 2019/5/4
Time: 20:12
功能:
-->

<!-- html代码片段 -->

<!--  特别提示:
如果要给默认值:需要把数据定义为数组多列模式
// values 存放值
// defaultIndex初始选中项的索引，默认为 0

cols : [
{
    values : [
    '杭州' ,
    '宁波' ,
    '温州' ,
    '嘉兴' ,
    '湖州'
    ] ,
    defaultIndex : 2
}
]
 -->
<template>

  <div>
    <view>基础使用</view>
    <!--
    如果没有设置 default-index
       会默认选择第1项-->
    <van-picker :columns="columns1"
                @change="onChange1"/>
    <mybr/>
    <mybr/>
    <view>设置一个默认值</view>
    <van-picker :columns="cols"
                @change="onChange2"/>
    <mybr/>
    <mybr/>
    <mybr/>
    <view>弹出选择</view>
    <van-button size="large"
                @click="tanchu"
                type="primary">弹出
    </van-button>
    <van-popup :show="popupshow3"
               position="bottom">

      <!--     -->

      <van-picker :columns="columns3"
                  show-toolbar
                  title="标题"
                  @cancel="onCancel3"
                  @confirm="onConfirm3"/>
    </van-popup>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "picker" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        columns1 : [
          '杭州' , '宁波' , '温州' , '嘉兴' , '湖州'
        ] ,

        cols : [
          {
            values : [
              '杭州' ,
              '宁波' ,
              '温州' ,
              '嘉兴' ,
              '湖州'
            ] ,
            defaultIndex : 2
          }
        ] ,

        popupshow3 : false ,
        columns3 : [
          '杭州' , '宁波' , '温州' , '嘉兴' , '湖州'
        ] ,
      }
    } ,
    //方法
    methods : {
      onChange1 ( event ) {

        // console.log( event )
        // console.log( event.mp.detail )

        //可以得到选择的值和索引
        let obj = event.mp.detail;
        let selectval = obj.value;
        let selectindex = obj.index;

        console.log( selectval )
        console.log( selectindex )
      } ,
      onChange2 ( event ) {
        console.log( event )
        console.log( event.mp.detail )

        //可以得到选择的值
        let obj = event.mp.detail;

        //取到选择的值 //因为是多列了，所以是数组 我们取第1个
        let selectval = obj.value[ 0 ];
        console.log( selectval )

        // console.log( obj.picker )
        //getIndexes 方法得到 选择的索引  //因为是多列了，所以是数组 我们取第1个
        let selectindex = obj.picker.getIndexes();
        console.log( selectindex[ 0 ] )

      } ,
      tanchu () {
        this.popupshow3 = true;
      } ,
      onCancel3 () {
        this.popupshow3 = false;
      } ,
      onConfirm3 ( event ) {
        console.log( event )

        //可以得到选择的值和索引
        let obj = event.mp.detail;
        let selectval = obj.value;
        let selectindex = obj.index;

        console.log( selectval )
        console.log( selectindex )

        this.popupshow3 = false;
      }
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
       src="./picker.css">
</style>
