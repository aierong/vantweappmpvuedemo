<template>
  <div>
    <view>Vant Weapp组件库官方示例改写到Mpvue框架下</view>
    <mybr/>
    <mybr/>
    <view>https://github.com/aierong/vantweappmpvuedemo</view>
    <mybr/>
    <mybr/>
    <button open-type="share">分享我吧</button>

    <mybr/>
    <mybr/>
    <mybr/>
    <mybr/>
    <button @click="sm">扫码功能</button>
    <mybr/>

    <button @click="imgselect">选择相册</button>
  </div>
</template>

<script>

    import mybr from '@/components/mybr/mybr.vue'

    export default {
        name : "readmeme" ,
        components : {
            mybr
        } ,
        onShareAppMessage () {
            return {
                title : 'Vant Weapp在mpvue中使用demo' ,
                path : '/pages/index/main' ,
                imageUrl : '/static/img/logo.png'
            }
        } ,
        data () {
            return {}
        } ,
        //方法
        methods : {
            sm () {
                const url = "../scanbarcode/main"
                wx.navigateTo( { url : url } )
            } ,
            imgselect () {
                const url = "../debugpage/selectimg/main"
                wx.navigateTo( { url : url } )
            } ,
        } ,
    }
</script>

<style scoped
       src="./readmeme.css">
</style>
