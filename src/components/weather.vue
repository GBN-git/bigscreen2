<template>
  <div class="row">
    <div class="col-md-4">
      <div class="col-md-12" id="">
        <h3 class="h3">1</h3>
        <div id="chart1" :style="{width: '300px', height: '300px'}"></div>
      </div>
      <div class="col-md-12">
        <h3 class="h3">1</h3>

      </div>
    </div>
    <div class="col-md-4">
      <h3 class="h3">1</h3>


    </div>
    <div class="col-md-4">
      <div class="col-md-12">
        <h3 class="h3">1</h3>

      </div>
      <div class="col-md-12">
        <h3 class="h3">1</h3>

      </div>
    </div>
  </div>

</template>

<script>
import * as echarts from "echarts";
export default {
  name: "weather",
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  mounted(){
    this.drawLine();
  },
  methods: {
    drawLine(){
      // 基于准备好的dom，初始化echarts实例
      let chart1 = echarts.init(document.getElementById('chart1'))
      // 绘制图表
      chart1.setOption({
        tooltip: {},
        xAxis: {
          type: 'category',
          data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
        },
        yAxis: {
          type: 'value'
        },
        series: [{
          data: [820, 932, 901, 934, 1290, 1330, 1320],
          type: 'line',
          smooth: true
        }]
      });
    }
  }

}

</script>
<style>
@import "../css/weather.css";
</style>