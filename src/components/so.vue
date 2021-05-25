<template>
  <div class="row">
    <div class="col-md-6">
      <h3 class="h3">1</h3>
      <div id="myChart" :style="{width: '300px', height: '300px'}"></div>
    </div>
    <div class="col-md-6">
      <h3 class="h3">1</h3>
      <div id="chart7" :style="{width: '300px', height: '300px'}"></div>
    </div>
  </div>

</template>
<script>
import * as echarts from "echarts";

export default {
  name: "so",
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
      let myChart = echarts.init(document.getElementById('myChart'))
      // 绘制图表
      myChart.setOption({
        tooltip: {},
        xAxis: {
          data: ["衬衫","羊毛衫","雪纺衫","裤子","高跟鞋","袜子"]
        },
        yAxis: {},
        series: [{
          name: '销量',
          type: 'bar',
          data: [5, 20, 36, 10, 10, 20]
        }]
      }
      );

      let chart7 = echarts.init(document.getElementById('chart7'))
      // 绘制图表
      chart7.setOption({
            tooltip: {},
            xAxis: {
              data: ["衬衫","羊毛衫","雪纺衫","裤子","高跟鞋","袜子"]
            },
            yAxis: {},
            series: [{
              name: '销量',
              type: 'bar',
              data: [5, 20, 36, 10, 10, 20]
            }]
          }
      );
    }
  }
}

</script>

<style>
@import "../css/so.css";
</style>