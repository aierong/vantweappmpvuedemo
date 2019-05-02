<template>
  <div class="tree">
    <van-tree-select
      :items="items"
      :main-active-index="mainActiveIndex"
      :active-id="activeId"
      @clickItem="onClickItem"
      @clickNav="onClickNav"
      content-item-class="content-item-class"
    ></van-tree-select>
  </div>
</template>

<script>
  import card from '@/components/card'
  import config from '@/utils/config-com-kinds'

  export default {
    data () {
      return {
        items: [
          {
            // 导航名称
            text: '所有组件',
            // 该导航下所有的可选项
            children: [...config.pro1,...config.pro2,...config.pro3,...config.pro4,...config.pro5,...config.pro6]
          }, {
            // 导航名称
            text: config.pro1Name,
            // 该导航下所有的可选项
            children: config.pro1
          }, {
            text: config.pro2Name,
            children: config.pro2
          }, {
            text: config.pro3Name,
            children: config.pro3
          }, {
            text: config.pro4Name,
            children: config.pro4
          }, {
            text: config.pro5Name,
            children: config.pro5
          }, {
            text: config.pro6Name,
            children: config.pro6
          }
        ],
        mainActiveIndex: 0,
        activeId: 0,
        pageUrls:[
          '/pages/button/main',
          '/pages/cell/main',
          '/pages/icon/main',
          '/pages/layout/main',
          '/pages/popup/main',
          '/pages/transition/main',
          '/pages/checkbox/main',
          '/pages/datetime-picker/main',
          '/pages/field/main',
          '/pages/picker/main',
          '/pages/radio/main',
          '/pages/rate/main',
          '/pages/search/main',
          '/pages/slider/main',
          '/pages/stepper/main',
          '/pages/switch/main',
          '/pages/switch-cell/main',
          '/pages/action-sheet/main',
          '/pages/dialog/main',
          '/pages/loading/main',
          '/pages/notify/main',
          '/pages/swipe-cell/main',
          '/pages/toast/main',
          '/pages/collapse/main',
          '/pages/notice-bar/main',
          '/pages/panel/main',
          '/pages/progress/main',
          '/pages/steps/main',
          '/pages/tag/main',
          '/pages/index/main',
          '/pages/badge/main',
          '/pages/nav-bar/main',
          '/pages/tab/main',
          '/pages/tabbar/main',
          '/pages/area/main',
          '/pages/card/main',
          '/pages/submit-bar/main',
          '/pages/goods-action/main'
        ]
      }
    },

    components: {
      card
    },

    methods: {
      //左侧导航点击时，触发的事件
      onClickNav(event) {
        this.mainActiveIndex=event.mp.detail.index || 0
      },
      //右侧选择项被点击时，会触发的事件
      //this.activeId从1开始，而不是从0开始！
      onClickItem(event) {
        this.activeId=event.mp.detail.id
        console.log('this.activeId: ',this.activeId);

        wx.navigateTo({url: this.pageUrls[this.activeId>0? this.activeId-1:this.activeId]})
        console.log('********************');
      }
    },
    created () {
    }
  }
</script>

<style scoped>
.tree{
  display: flex;
  flex-direction: column;
  width:100%;
  height:100%;
}
</style>
