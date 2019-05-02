<template><div>
<van-panel title="基础用法">
  <van-area
    :value="value"
    :loading="loading"
    :area-list="areaList"
    @change="onChange"
    @confirm="onConfirm"
    @cancel="onCancel"
  />
</van-panel>

<van-panel title="选中省市县">
  <van-area
    :value="value"
    :loading="loading"
    :area-list="areaList"
    @change="onChange"
    @confirm="onConfirm"
  />
</van-panel>

<van-panel title="配置显示列">
  <van-area
    title="标题"
    columns-num="2"
    :loading="loading"
    :area-list="areaList"
    @change="onChange"
    @confirm="onConfirm"
  />
</van-panel>


<van-toast id="van-toast" />
</div></template>
<script>
  import Toast from '../../../static/vant/toast/toast';

  export default{
    data(){
      return{
        areaList: {},
        loading: true,
        value: 330302
      }
    },
    /**
     * 生命周期方法
     * 注意：在微信小程序开发工具配置处“不校验合法域名...”——在真机上调试还要在微信小程序后台配置下面的域名才行。
     */
    onShow() {
      var that = this
      wx.request({
        url: 'https://cashier.youzan.com/wsctrade/uic/address/getAllRegion.json',
        headers: {
          'Content-Type': 'application/json'
        },
        success: response => {
          that.loading=false
          that.areaList=response.data.data
        }
      });
    },
    methods:{

      onChange(event) {
        const { values } = event.mp.detail;

        Toast(values.map(item => item.name).join('-'));
      },
      onConfirm(event) {
        console.log(event.mp);
      },
      onCancel(event) {
        console.log(event.mp);
      }
    }
  }
</script>
