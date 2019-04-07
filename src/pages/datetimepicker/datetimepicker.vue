<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <van-datetime-picker
      type="datetime"
      :value="currentDate"
      :min-date="minDate"
      :max-date="maxDate"
      :show-toolbar="isshow"
      @change="onchange"
      @input="onInput"/>

    <van-datetime-picker
      type="date"
      :value="currentDate2"
      :min-date=" minDate "
      @change="onchange"
    />
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  export default {
    name : "datetimepicker" ,
    //数据模型
    data () {
      return {
        minHour : 10 ,
        maxHour : 20 ,
        minDate : new Date().getTime() ,
        maxDate : new Date( 2019 , 10 , 1 ).getTime() ,
        currentDate : new Date().getTime() ,

        currentDate2 : new Date().getTime() ,
        isshow : false
      }
    } ,
    //方法
    methods : {
      onInput ( event ) {
        //代码搞这里
        console.log( event )
      } ,
      onchange ( ev ) {
        console.log( ev )

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
<style src="./datetimepicker.css"
       scoped>

</style>
