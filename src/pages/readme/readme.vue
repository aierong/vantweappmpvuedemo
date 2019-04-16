<template>
  <div>
    见本项目readme.md文件

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
        title : '猫叫助手|与猫咪交流的好帮手' ,
        path : '/pages/index/main' ,
        imageUrl : '/static/img/code.jpg'
      }
    } ,
    created () {

    }
  }
</script>

<style src="./readme.css">

</style>
