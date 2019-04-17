<template>
  <div>
    Vant Weapp组件库官方示例改写到Mpvue框架下
    <mybr/>

    <mybr/>
    <button open-type="share">分享我吧</button>
  </div>
</template>

<script>

  import mybr from '@/components/mybr/mybr.vue'

  export default {
    name : "search" ,
    components : {
      mybr
    } ,
    data () {
      return {
        logs : [] ,

      }
    } ,
    onShareAppMessage () {
      return {
        title : 'Vant Weapp在mpvue中使用demo' ,
        path : '/pages/index/main' ,
        imageUrl : '/static/img/logo.png'
      }
    } ,
    created () {

    }
  }
</script>

<style src="./readme.css">

</style>
