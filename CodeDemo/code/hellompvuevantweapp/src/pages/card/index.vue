<template>

<view class="container">
  <van-panel title="基础用法">
    <van-card
      num="2"
      price="2.00"
      desc="描述信息"
      title="2018秋冬新款男士休闲时尚军绿飞行夹克秋冬新款男"
      :thumb="imageURL"
    />
  </van-panel>

  <van-panel title="高级用法">
    <van-card
      num="2"
      tag="标签"
      price="2.00"
      origin-price="10.00"
      desc="描述信息"
      title="2018秋冬新款男士休闲时尚军绿飞行夹克秋冬新款男"
      :thumb="imageURL"
    >
      <view slot="tags">
        <van-tag plain type="danger" custom-class="tag">标签1</van-tag>
        <van-tag plain type="danger">标签2</van-tag>
      </view>
      <view slot="footer" class="van-card__footer">
        <van-button size="mini" round custom-class="button">按钮</van-button>
        <van-button size="mini" round>按钮</van-button>
      </view>
    </van-card>
  </van-panel>
</view>
</template>
<script>
  export default {
    data(){
      return{
        //https:这几个字符可以省略
        //https://m.360buyimg.com/babel/jfs/t1/19915/9/6821/299427/5c62b733E3473ee18/002fa63d99ad984d.jpg!q100.jpg.webp
        imageURL: 'https://img.yzcdn.cn/upload_files/2017/07/02/af5b9f44deaeb68000d7e4a711160c53.jpg'
      }
    },
    methods:{

    }
  }
</script>
<style>
  .container {
    height: 100vh;
    background-color: #fff5ec;
  }

  .tag,
  .button {
    margin-right: 5px;
  }

  .van-card__footer {
    margin-top: 5px;
  }

</style>
