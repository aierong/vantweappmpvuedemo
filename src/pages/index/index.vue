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
            txt : 'tab' ,
            pageurl : 'tab'
          } ,
          {
            txt : 'cell' ,
            pageurl : 'cell'
          } ,
          {
            txt : 'tag标签' ,
            pageurl : 'tag'
          }

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
