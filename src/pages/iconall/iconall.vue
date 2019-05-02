<!--
作者:chenghao
Date: 2019/5/2
Time: 22:56
功能:
-->

<!-- html代码片段 -->
<template>

  <div>
    <van-tabs :active="active"
              @change="onSwitch">
      <van-tab title="基础图标"
               custom-class="demo-tab-pane">
        <van-col v-for="item in icons.basic"
                 :key="item"
                 custom-class="col"
                 span="6">
          <van-icon :name="item"
                    size="32px"
                    custom-class="icon"/>
          <div class="text">{{ item }}</div>
        </van-col>
      </van-tab>
      <van-tab title="线框风格"
               custom-class="demo-tab-pane">
        <van-col v-for="item in icons.outline"
                 :key="item"
                 custom-class="col"
                 span="6">
          <van-icon :name="item"
                    size="32px"
                    custom-class="icon"/>
          <div class="text">{{ item }}</div>
        </van-col>
      </van-tab>
      <van-tab title="实底风格"
               custom-class="demo-tab-pane">
        <van-col v-for="item in icons.filled"
                 :key="item"
                 custom-class="col"
                 span="6">
          <van-icon :name="item"
                    size="32px"
                    custom-class="icon"/>
          <view class="text">{{ item }}</view>
        </van-col>
      </van-tab>
    </van-tabs>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
  import icons from '@/common/icons-config.js'

  export default {
    name : "iconall" ,
    //数据模型
    data () {
      return {
        icons ,
        active : 0
      }
    } ,
    //方法
    methods : {
      onSwitch ( event ) {
        this.active = event.mp.detail.index
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
       src="./iconall.css">
</style>
