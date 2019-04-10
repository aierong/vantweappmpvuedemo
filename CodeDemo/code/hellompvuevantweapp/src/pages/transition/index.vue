<template>
  <van-panel title="基础用法" padding>
    <van-cell title="Fade" @click="onClickFade" is-link/>
    <van-cell title="Fade Up" @click="onClickFadeUp" is-link/>
    <van-cell title="Fade Down" @click="onClickFadeDown" is-link/>
    <van-cell title="Fade Left" @click="onClickFadeLeft" is-link/>
    <van-cell title="Fade Right" @click="onClickFadeRight" is-link/>
    <van-cell title="Slide Up" @click="onClickSlideUp" is-link/>
    <van-cell title="Slide Down" @click="onClickSlideDown" is-link/>
    <van-cell title="Slide Left" @click="onClickSlideLeft" is-link/>
    <van-cell title="Slide Right" @click="onClickSlideRight" is-link/>

    <van-transition :show="show" :name="name" custom-class="block">
      <!--<van-icon :name="shopping-cart" size="32px" custom-class="icon"/>-->
      <div>ABC</div>
    </van-transition>
  </van-panel>
</template>
<script>

  export default {
    data(){
      return{
        show: false,
        name: 'fade'
      }
    },
    methods:{
      onClickFade() {
        this.trigger('fade');
      },

      onClickFadeUp() {
        this.trigger('fade-up');
      },

      onClickFadeDown() {
        this.trigger('fade-down');
      },

      onClickFadeLeft() {
        this.trigger('fade-left');
      },

      onClickFadeRight() {
        this.trigger('fade-right');
      },

      onClickSlideUp() {
        this.trigger('slide-up');
      },

      onClickSlideDown() {
        this.trigger('slide-down');
      },

      onClickSlideLeft() {
        this.trigger('slide-left');
      },

      onClickSlideRight() {
        this.trigger('slide-right');
      },

      trigger(name) {
        this.name=name
        this.show=true
        setTimeout(() => {this.show=false}, 500);
      }
    }
  }
</script>
<style>
  .block {
    top: 50%;
    left: 50%;
    width: 200rpx;
    height: 200rpx;
    position: fixed;
    margin: -50rpx 0 0 -50rpx;
    background-color: #faf10d;
  }
  /*.icon {*/
    /*display: block;*/
    /*margin: 15px 0;*/
    /*color: #75fff4;*/
  /*}*/
</style>
