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
    <van-checkbox :value="checked1"
                  @change="onChange1">复选框
    </van-checkbox>
    <mybr/>
    <mybr/>
    <div>自定义颜色</div>
    <van-checkbox :value="checked2"
                  checked-color="#07c160"
                  @change="onChange2">
      复选框
    </van-checkbox>
    <mybr/>
    <mybr/>
    <div>复选框组</div>
    <van-checkbox-group :value="result1"
                        @change="onChangezhu1">
      <van-checkbox v-for="(item,index) in list1"
                    :key="index"
                    :name="item">
        复选框 {{ item }}
      </van-checkbox>
    </van-checkbox-group>
    <van-button @click="dj"
                type="info">刷新列表
    </van-button>
    <!--
checkbox-group 中刷新数据后之前选中的没有选中状态

参考:
https://github.com/youzan/vant-weapp/issues/1486
-->

    <mybr/>
    <mybr/>
    <div>与Cell组件一起使用</div>
    <!--
    实现单击cell或者checkbox都可以选择
    -->
    <van-checkbox-group :value="resulta"
                        @change="onChangea">
      <van-cell-group>
        <van-cell v-for="(item,index) in lista"
                  :key="index"
                  :data-name="item"
                  @click="celltoggle"
                  :title="'复选框'+ item">
          <van-checkbox :name="item"/>
        </van-cell>
      </van-cell-group>
    </van-checkbox-group>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "index" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        checked1 : true ,
        checked2 : true ,

        result1 : [ 'A' , 'B' ] ,
        list1 : [ 'A' , 'B' , 'C' , 'D' ] ,

        lista : [ 'a' , 'b' , 'c' ] ,
        resulta : [ 'a' , 'b' ]
      }
    } ,
    //方法
    methods : {
      onChange ( ev ) {
        //代码搞这里

        console.log( ev )

        this.checked1 = ev.mp.detail;
      } ,
      onChange2 ( ev ) {
        this.checked2 = ev.mp.detail;
      } ,
      onChangezhu1 ( ev ) {
        console.log( ev )

        this.result1 = ev.mp.detail;
      } ,
      onChangea ( ev ) {
        console.log( ev )

        this.resulta = ev.mp.detail;
      } ,
      celltoggle ( ee ) {
        console.log( ee )

        console.log( ee.mp.currentTarget.dataset.name )

        let val = ee.mp.currentTarget.dataset.name;

        let index = this.resulta.indexOf( val );
        if ( index <= -1 ) {
          //不存在就添加进去
          this.resulta.push( val )
        }
        else {
          //之前存在 现在把它干了
          this.resulta.splice( index , 1 );
        }

      } ,
      dj () {
        this.list1 = [ 'B' , 'C' , 'E' , 'F' , 'G' ]

        //     checkbox-group 中刷新数据后之前选中的没有选中状态
        // 参考:
        //   https://github.com/youzan/vant-weapp/issues/1486
        //
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
<style src="./checkbox.css"
       scoped>

</style>
