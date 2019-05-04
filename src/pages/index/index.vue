<template>
  <div>

    <van-tabs @change="onChangeval"
              :active="activeval">
      <van-tab title="基础组件">
        <van-cell :title="item.txt"
                  icon="location-o"
                  @click="onclick(item.pageurl)"
                  is-link
                  v-for="(item,index) in jichulist"
                  :key="index"/>
      </van-tab>
      <van-tab title="表单组件">
        <van-cell :title="item.txt"
                  icon="location-o"
                  @click="onclick(item.pageurl)"
                  is-link
                  v-for="(item,index) in biaodanlist"
                  :key="index"/>
      </van-tab>
      <van-tab title="展示组件">
        <van-cell :title="item.txt"
                  icon="location-o"
                  @click="onclick(item.pageurl)"
                  is-link
                  v-for="(item,index) in zhangshilist"
                  :key="index"/>
      </van-tab>
      <van-tab title="导航组件">

        <van-cell v-for="(item,index) in DaoHanList"
                  :key="index"
                  :title="item.txt"
                  icon="location-o"
                  @click="onclick(item.pageurl)"
                  is-link/>

      </van-tab>


      <van-tab title="反馈组件">
        <van-cell v-for="(item,index) in FanKuiList"
                  :key="index"
                  :title="item.txt"
                  icon="location-o"
                  @click="onclick(item.pageurl)"
                  is-link/>
      </van-tab>

      <!--
      <van-tab title="标签6">内容 6</van-tab>
      -->

    </van-tabs>


  </div>
</template>

<script>

  export default {
    data () {
      return {
        //从0开始的
        activeval : 0 ,
        zhangshilist : [
          {
            txt : 'Panel 面板' ,
            pageurl : 'mypanel'
          } ,

          {
            txt : 'Steps 步骤条' ,
            pageurl : 'steps'
          } ,
          {
            txt : 'Collapse 折叠面板' ,
            pageurl : 'mycollapse'
          } ,
          {
            txt : 'tag标签' ,
            pageurl : 'tag'
          } ,
          {
            txt : 'NoticeBar 通告栏' ,
            pageurl : 'noticebar'
          } ,
        ] ,
        biaodanlist : [
          {
            txt : 'Checkbox 复选框' ,
            pageurl : 'checkbox'
          } ,
          {
            txt : 'Radio 单选框' ,
            pageurl : 'radios'
          } ,

          {
            txt : 'DatetimePicker 时间选择' ,
            pageurl : 'datetimepicker'
          } ,
          {
            txt : 'Field 输入框' ,
            pageurl : 'field'
          } ,
          {
            txt : 'Search 搜索' ,
            pageurl : 'search'
          } ,
        ] ,
        jichulist : [
          {
            txt : '按钮' ,
            pageurl : 'button'
          } ,
          {
            txt : 'Cell单元格' ,
            pageurl : 'mycell'
          } ,
          {
            txt : 'Icon图标Demo' ,
            pageurl : 'icon'
          } ,
          {
            txt : 'Icon(所有图标)' ,
            pageurl : 'iconall'
          } ,

          {
            txt : 'Layout 布局' ,
            pageurl : 'layout'
          } ,
          {
            txt : 'Layout布局(自做demo)' ,
            pageurl : 'layoutdemo'
          } ,

          {
            txt : 'Popup 弹出层' ,
            pageurl : 'mypopup'
          } ,
          {
            txt : 'Transition 动画' ,
            pageurl : 'mytransition'
          } ,
        ] ,

        DaoHanList : [
          {
            txt : 'Tab 标签页' ,
            pageurl : 'tab'
          } ,

          {
            txt : 'NavBar 导航栏' ,
            pageurl : 'navbar'
          } ,

        ] ,
        FanKuiList : [
          {
            txt : 'Notify 消息提示' ,
            pageurl : 'mynotify'
          } ,

          {
            txt : 'Toast 轻提示' ,
            pageurl : 'mytoast'
          } ,
          {
            txt : 'Loading 加载' ,
            pageurl : 'loading'
          } ,
          {
            txt : 'Dialog 弹出框' ,
            pageurl : 'mydialog'
          } ,

        ] ,

      }
    } ,

    methods : {
      onclick ( pageurl ) {
        const url = `../${ pageurl }/main`
        wx.navigateTo( { url : url } )
      } ,
      buttonclick () {
        const url = "../button/main"
        wx.navigateTo( { url : url } )
      } ,
      onChangeval ( event ) {
        this.activeval = event.mp.detail.index;

      } ,
    } ,

    created () {
      // let app = getApp()
    }
  }
</script>

<style src="./index.css"
       scoped>
</style>


