<template>
  <div class="details">
    <div class="row" v-for="(key,value) in details">
      <div class="cell left">{{ value }}</div>
      <div class="cell right">{{ key }}</div>
    </div>
  </div>
</template>

<script>

  export default {
    props: ['weather'],
    data() {
      return {
      };
    },
    computed: {
      details () {
        return {
          '日出：': this.weather.daily_forecast[0].sr,
          '日落：': this.weather.daily_forecast[0].ss,
          '降雨概率：': `${this.weather.daily_forecast[0].pop}%`,
          '相对湿度：': this.weather.daily_forecast[0].hum,
          '气压：': `${this.weather.daily_forecast[0].pres}百帕`,
          '能见度：': `${this.weather.daily_forecast[0].vis}公里`,
          '紫外线强度：': this.weather.lifestyle[5].brf,
          '体感温度：': `${this.weather.now.fl}°`,
          '风速：': `${this.weather.now.wind_dir} ${this.weather.now.wind_spd}公里/小时`,
          '空气质量指数：': this.weather.lifestyle[7].brf,
          '穿衣指数：': this.weather.lifestyle[1].brf,
          '感冒指数：': this.weather.lifestyle[2].brf,
          '运动指数：': this.weather.lifestyle[3].brf
        };
      }
    }
  };
</script>

<style lang="less">
  .details {
    padding: 10px 15px;
    color: #fff;
    font-size: 14px;
    .row {
      display: flex;
      margin: 5px 0;
      .cell {
        flex: 1;
        line-height: 16px;
        &.left {
          padding-right: 15px;
          text-align: right;
        }
        &.right {
          text-align: left;
        }
      }
    }
  }
</style>
