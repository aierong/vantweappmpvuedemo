<template>
  <div>
    <van-panel title="1.基本用法">
      <van-checkbox name="checkbox1" :value="checkbox1" data-key="checkbox1" custom-class="demo-checkbox" @change="onChange">
        复选框
      </van-checkbox>
    </van-panel>

    <van-panel title="2.禁用状态">
      <van-checkbox disabled :value="false" custom-class="demo-checkbox">
        复选框
      </van-checkbox>
      <van-checkbox disabled :value="true" custom-class="demo-checkbox">
        复选框
      </van-checkbox>
    </van-panel>

    <van-panel title="3.自定义颜色">
      <van-checkbox :value="checkbox2" data-key="checkbox2" checked-color="#07c160" custom-class="demo-checkbox" @change="onChange" >
        复选框
      </van-checkbox>
    </van-panel>

    <van-panel title="4.自定义图标">
      <van-checkbox use-icon-slot :value="checkbox3" data-key="checkbox3" custom-class="demo-checkbox" @change="onChange">
        自定义图标
        <image mode="widthFix" slot="icon" :src="checkbox3? icon.active : icon.normal" class="icon"/>
      </van-checkbox>
    </van-panel>

    <van-panel title="5.复选框组">
      <van-checkbox-group :value="result" data-key="result" @change="onChange">
        <van-checkbox v-for="item in list" :key="index" :name="item"  shape="square" custom-class="demo-checkbox">
          选项 {{ item }}
        </van-checkbox>
      </van-checkbox-group>
    </van-panel>

    <van-panel title="6.设置最大可选项">
      <van-checkbox-group :value="result2" data-key="result2" max="2" @change="onChange">
        <van-checkbox v-for="item in list" :key="index" :name="item"  shape="square" custom-class="demo-checkbox">
          复选框 {{ item }}
        </van-checkbox>
      </van-checkbox-group>
    </van-panel>

    <van-panel title="7.搭配单元格组件使用">
      <van-checkbox-group :value="result3" data-key="result3" @change="onChange">
        <van-cell-group>
          <van-cell v-for="item in list" :key="index" :title="'复选框'+item" clickable :data-name="item" @click="toggle">
            <van-checkbox @tap="noop" :class="'checkboxes-'+item" :name="item"  custom-class="demo-checkbox">单元格组件复选框 {{ item }}</van-checkbox>
          </van-cell>
        </van-cell-group>
      </van-checkbox-group>
    </van-panel>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        checkbox1: true,
        checkbox2: true,
        checkbox3: true,
        list: ['A', 'B', 'C','D'],
        result: ['A', 'B'],
        result2: [],
        result3: [],
        icon: {
          normal:'/static/images/custom_normal_checkbox.png',
          active:'/static/images/custom_active_checkbox.png'
        }
      }
    },
    methods: {
      onChange(event) {
        const {key} = event.mp.currentTarget.dataset;
        //this.setData({[key]: event.mp.detail});
        this[key]=event.mp.detail;

        console.log('result: ',this.result.sort())
      },

      onClick(event) {
        const {value} = event.mp.currentTarget.dataset;
        this.radio3=value
      },

      toggle(event) {
        const {name} = event.mp.currentTarget.dataset;
        //const box = this.selectComponent(`.checkboxes-${name}`);
        const box =this.$mp.page.selectComponent(`.checkboxes-${name}`)
        console.log('box: ',box);
        box.toggle();
      },

      noop() {
      }

    }
  }
</script>
<style>
  .demo-checkbox-group {
    margin: 10px 0 0 20px;
  }

  .demo-checkbox {
    margin: 10px 0 0 20px;
  }

  .valueclass {
    flex: none !important;
  }

  .icon {
    width: 20px;
  }

</style>
