<!--
作者:chenghao
功能:vue页
-->

<!-- html代码片段 -->
<template>

  <div>
    <van-steps :steps="steps"
               :active="active"/>

    <mybr/>
    <mybr/>
    <div>竖向步骤条</div>
    <van-steps :steps="steps2"
               :active="active2"
               direction="vertical"
               active-color="#f44"/>
    <mybr/>
    <button @click="nextbu">下一步</button>
    <mybr/>
    <mybr/>
    <!--
    van-steps暂时不支持，一个个加载
    -->

    <!--    <van-steps :active="active2"-->
    <!--               direction="vertical">-->


    <!--      <van-step>-->
    <!--        <h3>【城市】物流状态1</h3>-->
    <!--        <p>2016-07-12 12:40</p>-->
    <!--      </van-step>-->
    <!--      <van-step>-->
    <!--        <h3>【城市】物流状态2</h3>-->
    <!--        <p>2016-07-11 10:00</p>-->
    <!--      </van-step>-->
    <!--      <van-step>-->
    <!--        <h3>快件已发货</h3>-->
    <!--        <p>2016-07-10 09:30</p>-->
    <!--      </van-step>-->
    <!--    </van-steps>-->
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "steps" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        active : 0 ,
        steps : [
          {
            text : '步骤一' ,
            desc : '描述信息'
          } ,
          {
            text : '步骤二' ,
            desc : '描述信息'
          } ,
          {
            text : '步骤三' ,
            desc : '描述信息'
          } ,
          {
            text : '步骤四' ,
            desc : '描述信息'
          }
        ] ,
        active2 : 2 ,
        steps2 : [
          {
            text : '步骤一' ,
            desc : '描述信息'
          } ,
          {
            text : '步骤二' ,
            desc : '描述信息'
          } ,
          {
            text : '步骤三' ,
            desc : '描述信息'
          } ,
          {
            text : '步骤四' ,
            desc : '描述信息'
          }
        ] ,
      }
    } ,
    //方法
    methods : {
      nextbu () {
        //代码搞这里

        this.active2 = ++this.active2;

        if ( this.active2 >= 4 ) {
          this.active2 = 0;
        }
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
<style src="./steps.css"
       scoped>

</style>
