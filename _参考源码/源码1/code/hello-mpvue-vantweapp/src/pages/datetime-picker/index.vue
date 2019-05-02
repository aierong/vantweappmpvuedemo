<template>
  <div>
    <van-panel title="选择完整时间">
      <van-datetime-picker
        type="datetime"
        data-type="datetime"
        :loading="loading"
        :value="currentDate1"
        :min-date="minDate"
        @input="onInput"
      />
    </van-panel>

    <van-panel title="选择日期（年月日）">
      <van-datetime-picker
        type="date"
        data-type="date"
        :value="currentDate2"
        :min-date="minDate"
        @input="onInput"
      />
    </van-panel>

    <van-panel title="选择日期（年月）">
      <van-datetime-picker
        type="year-month"
        data-type="year-month"
        :value="currentDate3"
        :min-date="minDate"
        @confirm="onConfirm"
        @cancel="onCancel"
      />
    </van-panel>

    <van-panel title="选择时间">
      <van-datetime-picker
        type="time"
        data-type="time"
        :value="currentDate4"
        :min-hour="minHour"
        :max-hour="maxHour"
        @input="onInput"
      />
    </van-panel>

    <van-toast id="van-toast"/>
  </div>
</template>
<script>
  import Toast from '../../../static/vant/toast/toast';

  export default {
    data() {
      return {
        minHour: 10,
        maxHour: 20,
        minDate: new Date(2018, 0, 1).getTime(),
        maxDate: new Date(2019, 10, 1).getTime(),
        currentDate1: new Date(2019, 2, 10).getTime(),
        currentDate2: null,
        currentDate3: new Date(2019, 2, 1),
        currentDate4: '12:00',
        loading: false
      }
    },
    methods: {
      onInput(event) {
        const {detail, currentTarget} = event.mp;
        const result = this.getResult(detail, currentTarget.dataset.type);

        Toast(result);
      },

      getResult(time, type) {
        const date = new Date(time);
        switch (type) {
          case 'datetime':
            return date.toLocaleString();
          case 'date':
            return date.toLocaleDateString();
          case 'year-month':
            return `${date.getFullYear()}/${date.getMonth() + 1}`;
          case 'time':
            return time;
          default:
            return '';
        }
      },
      onConfirm(val){
        const {detail, currentTarget} = val.mp;
        const result = this.getResult(detail, currentTarget.dataset.type);

        console.log("val: ",result) // 打印出了时间
      },
      onCancel(){

      }

    }
  }
</script>
<style>

</style>
