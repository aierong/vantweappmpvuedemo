<!--
作者:chenghao
Date: 2019/5/5
Time: 20:53
功能:
-->

<!-- html代码片段 -->
<template>

  <div>
    <van-picker :columns="columns"
                @change="onChange"/>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  const citys = {
    '浙江' : [ '杭州' , '宁波' , '温州' , '嘉兴' , '湖州' ] ,
    '福建' : [ '福州' , '厦门' , '莆田' , '三明' , '泉州' ]
  };

  export default {
    name : "pickermorecols" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        columns : [
          {
            values : Object.keys( citys )
          } ,
          {
            values : citys[ "浙江" ] ,

            defaultIndex : 2
          }
        ]
      }
    } ,
    //方法
    methods : {
      onChange ( event ) {
        const { picker , value , index } = event.mp.detail;

        //通过这个方法，选择第2列的数据
        picker.setColumnValues( 1 , citys[ value[ 0 ] ] )
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
       src="./pickermorecols.css">
</style>
