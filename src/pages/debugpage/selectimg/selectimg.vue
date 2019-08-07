<!--
作者:chenghao
Date: 2019/8/7
Time: 10:38
功能:
-->

<!-- html代码片段 -->
<template>

  <div>
    <button @click="imgselect">选择相册</button>
    <button @click="imgselectmenu">选择相册(选择菜单)</button>
    <mybr/>
    <mybr/>
    <!--    <h1></h1>-->
    <image :src="imgdata"
           mode="aspectFill"></image>
    <img :src="imgdata2"
         alt=""/>
  </div>

</template>

<!-- js脚本代码片段 -->
<script>
    import mybr from '@/components/mybr/mybr.vue'

    export default {
        name : "selectimg" ,
        components : {
            mybr
        } ,
        //数据模型
        data () {
            return {
                imgdata : null ,
                imgdata2 : null
            }
        } ,
        //方法
        methods : {
            imgselect () {
                //代码搞这里
                //选择图片
                wx.chooseImage( {
                    //最多可以选择的图片张数,最多9张
                    count : 1 ,
                    sizeType : [ 'original' , 'compressed' ] ,  //可选择原图或压缩后的图片
                    sourceType : [ 'album' , 'camera' ] , //可选择性开放访问相册、相机
                    success : res => {
                        console.log( res )
                        console.log( res.tempFilePaths )

                        this.imgdata = res.tempFilePaths[ 0 ];

                        console.log( this.imgdata )
                    }
                } )
            } ,
            imgselectmenu () {
                wx.showActionSheet( {
                    //按钮的文字数组，数组长度最大为 6 个,
                    itemList : [ '从相册中选择' , '拍照' ] ,

                    success : res => {
                        //tapIndex就是用户点击的按钮序号,从上到下的顺序,从0开始
                        let index = res.tapIndex;
                        //console.log( index )

                        //调用方法
                        this.imgopen( index == 1 ? 'album' : 'camera' )
                    }
                } );
            } ,
            imgopen ( type ) {
                wx.chooseImage( {
                    //最多可以选择的图片张数,最多9张
                    count : 1 ,
                    sizeType : [ 'original' , 'compressed' ] ,  //可选择原图或压缩后的图片
                    sourceType : [ type ] , //可选择性开放访问相册、相机
                    success : res => {
                        console.log( res )
                        console.log( res.tempFilePaths )

                        this.imgdata2 = res.tempFilePaths[ 0 ];

                        console.log( this.imgdata )
                    }
                } )
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
       src="./selectimg.css">
</style>
