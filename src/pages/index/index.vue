<template>
  <div>

    <van-button type="default">默认按钮</van-button>
    <van-button type="primary">主要按钮</van-button>
    <van-button type="info">信息按钮</van-button>
    <van-button type="warning">警告按钮</van-button>
    <van-button @click="dj"
                type="danger">危险按钮
    </van-button>

    <van-cell
      title="单元格"
      value="内容"
      size="large"
    />
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
        motto : 'Hello miniprograme' ,

      }
    } ,

    methods : {
      dj () {
        console.log( 'dj' )
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
