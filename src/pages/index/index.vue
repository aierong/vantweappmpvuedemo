<template>
  <div>

    <div v-for="(item,index) in mydemolist"
         :key="index">
      <van-cell :title="item.txt"
                icon="location-o"
                @click="onclick(item.pageurl)"
                is-link/>
    </div>
    <!--    <van-cell title="按钮"-->
    <!--              icon="location-o"-->
    <!--              @click="buttonclick"-->
    <!--              is-link/>-->
    <!--    <van-cell-->
    <!--      title="单元格"-->
    <!--      value="内容"-->
    <!--      size="large"-->
    <!--      label="描述信息"-->
    <!--    />-->

    <!--    <van-cell-->
    <!--      title="单元格"-->
    <!--      icon="location-o"-->
    <!--    />-->

    <!--    <van-cell-group>-->
    <!--      <van-cell-->
    <!--        title="单元格"-->
    <!--        value="内容"-->
    <!--      />-->
    <!--      <van-cell-->
    <!--        title="单元格"-->
    <!--        value="内容"-->
    <!--        label="描述信息"-->
    <!--        border="false"-->
    <!--      />-->
    <!--    </van-cell-group>-->
  </div>
</template>

<script>

  export default {
    data () {
      return {
        mydemolist : [
          {
            txt : '按钮' ,
            pageurl : 'button'
          } ,

          {
            txt : 'Icon 图标' ,
            pageurl : 'icon'
          } ,

          {
            txt : 'DatetimePicker 时间选择' ,
            pageurl : 'datetimepicker'
          } ,

          {
            txt : 'Tab 标签页' ,
            pageurl : 'tab'
          } ,

          {
            txt : 'Cell 单元格' ,
            pageurl : 'cell'
          } ,

          {
            txt : 'tag标签' ,
            pageurl : 'tag'
          } ,

          {
            txt : 'Collapse 折叠面板' ,
            pageurl : 'mycollapse'
          } ,
          {
            txt : 'Panel 面板' ,
            pageurl : 'mypanel'
          } ,

          {
            txt : 'Steps 步骤条' ,
            pageurl : 'steps'
          } ,

          {
            txt : 'Popup 弹出层' ,
            pageurl : 'mypopup'
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
    } ,

    created () {
      // let app = getApp()
    }
  }
</script>

<style src="./index.css"
       scoped>
</style>


