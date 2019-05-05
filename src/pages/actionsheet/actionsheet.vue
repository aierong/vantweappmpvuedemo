<!--
作者:chenghao
Date: 2019/5/5
Time: 10:33
功能:
-->

<!-- html代码片段 -->
<template>

  <div>
    <view>基础用法</view>
    <van-button plain
                @click="dj1"
                type="primary">弹出actionsheet
    </van-button>
    <van-action-sheet :show="show1"
                      :actions="actions1"
                      @close="onClose1"
                      @select="onSelect1"/>
    <mybr/>
    <mybr/>
    <view>带标题的 ActionSheet</view>
    <!--
    如果传入了title属性，且不为空，则另外一种样式的ActionSheet，里面内容需要自定义
    -->
    <van-button plain
                @click="dj2"
                type="primary">弹出带标题的actionsheet
    </van-button>
    <van-action-sheet :show="show2"
                      @close="onClose2"
                      title="支持以下配送方式">
      <view class="content">一些内容</view>
    </van-action-sheet>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "actionsheet" ,
    components : {
      mybr
    } ,
    //数据模型
    data () {
      return {
        show1 : false ,

        //actions的格式，可以参考 https://youzan.github.io/vant-weapp/#/action-sheet
        actions1 : [
          {
            name : '选项1'
          } ,
          {
            name : '分享' ,
            subname : '描述信息' ,
            openType : 'share'
          } ,
          {
            loading : true
          } ,
          {
            name : '禁用选项' ,
            disabled : true
          }
        ] ,
        show2 : false ,
      }
    } ,
    //方法
    methods : {
      onClose1 () {
        this.show1 = false;
      } ,
      onSelect1 ( event ) {
        // console.log( event )
        let obj = event.mp.detail;

        // console.log( obj )

        //取到选择的值
        let name = obj.name;

        console.log( name )

        this.show1 = false;

      } ,
      dj1 () {
        this.show1 = true;
      } ,
      dj2 () {
        this.show2 = true;
      } ,
      onClose2 () {
        this.show2 = false;
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
<style src="./actionsheet.css"
       scoped>
</style>
