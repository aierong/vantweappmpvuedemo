<template>
  <div>


    <van-cell title="按钮"
              icon="location-o"
              @click="buttonclick"
              is-link/>
    <van-cell
      title="单元格"
      value="内容"
      size="large"
      label="描述信息"
    />

    <van-cell
      title="单元格"
      icon="location-o"
    />

    <van-cell-group>
      <van-cell
        title="单元格"
        value="内容"
      />
      <van-cell
        title="单元格"
        value="内容"
        label="描述信息"
        border="false"
      />
    </van-cell-group>
  </div>
</template>

<script>

  export default {
    data () {
      return {
        motto : '' ,

      }
    } ,

    methods : {
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
