<template>
  <div>
    <van-panel title="基础用法">
      <van-picker :columns="column1" @change="onChange1"/>
    </van-panel>

    <van-panel title="禁用选项">
      <van-picker :columns="column2" />
    </van-panel>
    <!--非常典型的表达如下-->
    <van-panel title="展示顶部栏">
      <van-picker show-toolbar title="标题" :columns="column1" @change="onChange1" @confirm="onConfirm" @cancel="onCancel"/>
    </van-panel>

    <!--高级用法-->
x    <van-panel title="多列联动">
      <van-picker :columns="column4" @change="onChange2"/>
    </van-panel>

    <van-panel title="加载状态">
      <van-picker loading :columns="column4"/>
    </van-panel>
    <!--这种特殊占位符是必须有的！-->
    <van-toast id="van-toast"/>
  </div>
</template>
<script>
  //在此只能使用相对路径方式！
  //.json文件中可以使用绝对路径！
  import Toast from '../../../static/vant/toast/toast'

  export default {
    data(){
      return{
        column1: ['杭州', '宁波', '温州', '嘉兴', '湖州'],
        column2: [
          { text: '杭州', disabled: true },
          { text: '宁波' },
          { text: '温州' }
        ],
        column3: {
          浙江: ['杭州', '宁波', '温州', '嘉兴', '湖州'],
          福建: ['福州', '厦门', '莆田', '三明', '泉州']
        },
        //当传入多列数据时，columns为一个对象数组，数组中的每一个对象配置每一列
        column4: [
          {
            values: ['浙江', '福建'],
            className: 'column1'
          },
          {
            values: ['杭州', '宁波', '温州', '嘉兴', '湖州'],
            className: 'column2',
            defaultIndex: 2
          }
        ]
      }
    },
    methods:{
      onChange1(event) {
        const { value, index } = event.mp.detail;
        Toast(`Value: ${value}, Index：${index}`);
      },

      onConfirm(event) {
        const { value, index } = event.mp.detail;
        Toast(`Value: ${value}, Index：${index}`);
      },

      onCancel() {
        Toast('取消');
      },

      onChange2(event) {
        const { picker, value } = event.mp.detail;
        picker.setColumnValues(1, this.column3[value[0]]);//this.data.column3是错误的写法！

        //getApp().picker = picker;//？？？
      }

    }
  }
</script>
<style>

</style>
