<template>
  <div class="row">
    <div class="col-md-4">
      <div class="row">
        <div class="col-md-12" id="">
          <h3 class="h3">各市</h3>
          <div id="chart1" :style="{width: '500px', height: '250px'}"></div>
        </div>
        <div class="col-md-12">
          <h3 class="h3">今日温度分析</h3>
          <div id="chart2" :style="{width: '500px', height: '250px'}"></div>
        </div>
      </div>
    </div>
    <div class="col-md-4">
      <h3 class="h3">天气分析</h3>
      <div id="chart3" :style="{width: '600px', height: '500px'}"></div>
    </div>
    <div class="col-md-4">
      <div class="row">
        <div class="col-md-12">
          <h3 class="h3">天气生活指数</h3>
          <div id="chart4" :style="{width: '500px', height: '250px'}"></div>
        </div>
        <div class="col-md-12">
          <h3 class="h3">降雨量</h3>
          <div id="chart5" :style="{width: '500px', height: '250px'}"></div>
        </div>
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

        tooltip: {
          trigger: 'axis',
          axisPointer: {
            type: 'cross',
            label: {
              backgroundColor: '#6a7985'
            }
          }
        },
        legend: {
          data: ['邮件营销', '联盟广告', '视频广告', '直接访问', '搜索引擎']
        },
        toolbox: {
          feature: {
            saveAsImage: {}
          }
        },
        grid: {
          left: '3%',
          right: '4%',
          bottom: '3%',
          containLabel: true
        },
        xAxis: [
          {
            type: 'category',
            boundaryGap: false,
            data: ['周一', '周二', '周三', '周四', '周五', '周六', '周日']
          }
        ],
        yAxis: [
          {
            type: 'value'
          }
        ],
        series: [
          {
            name: '邮件营销',
            type: 'line',
            stack: '总量',
            areaStyle: {},
            emphasis: {
              focus: 'series'
            },
            data: [120, 132, 101, 134, 90, 230, 210]
          },
          {
            name: '联盟广告',
            type: 'line',
            stack: '总量',
            areaStyle: {},
            emphasis: {
              focus: 'series'
            },
            data: [220, 182, 191, 234, 290, 330, 310]
          },
          {
            name: '视频广告',
            type: 'line',
            stack: '总量',
            areaStyle: {},
            emphasis: {
              focus: 'series'
            },
            data: [150, 232, 201, 154, 190, 330, 410]
          },
          {
            name: '直接访问',
            type: 'line',
            stack: '总量',
            areaStyle: {},
            emphasis: {
              focus: 'series'
            },
            data: [320, 332, 301, 334, 390, 330, 320]
          },
          {
            name: '搜索引擎',
            type: 'line',
            stack: '总量',
            label: {
              show: true,
              position: 'top'
            },
            areaStyle: {},
            emphasis: {
              focus: 'series'
            },
            data: [820, 932, 901, 934, 1290, 1330, 1320]
          }
        ]
      });
      let chart2 = echarts.init(document.getElementById('chart2'))
      chart2.setOption({

      });
      let chart3 = echarts.init(document.getElementById('chart3'))
      // 绘制图表
      chart3.setOption({
        tooltip: {
          trigger: 'axis',
          axisPointer: {            // Use axis to trigger tooltip
            type: 'shadow'        // 'shadow' as default; can also be 'line' or 'shadow'
          }
        },
        legend: {
          data: ['Direct', 'Mail Ad', 'Affiliate Ad', 'Video Ad', 'Search Engine']
        },
        grid: {
          left: '3%',
          right: '4%',
          bottom: '3%',
          containLabel: true
        },
        xAxis: {
          type: 'value'
        },
        yAxis: {
          type: 'category',
          data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
        },
        series: [
          {
            name: 'Direct',
            type: 'bar',
            stack: 'total',
            label: {
              show: true
            },
            emphasis: {
              focus: 'series'
            },
            data: [320, 302, 301, 334, 390, 330, 320]
          },
          {
            name: 'Mail Ad',
            type: 'bar',
            stack: 'total',
            label: {
              show: true
            },
            emphasis: {
              focus: 'series'
            },
            data: [120, 132, 101, 134, 90, 230, 210]
          },
          {
            name: 'Affiliate Ad',
            type: 'bar',
            stack: 'total',
            label: {
              show: true
            },
            emphasis: {
              focus: 'series'
            },
            data: [220, 182, 191, 234, 290, 330, 310]
          },
          {
            name: 'Video Ad',
            type: 'bar',
            stack: 'total',
            label: {
              show: true
            },
            emphasis: {
              focus: 'series'
            },
            data: [150, 212, 201, 154, 190, 330, 410]
          },
          {
            name: 'Search Engine',
            type: 'bar',
            stack: 'total',
            label: {
              show: true
            },
            emphasis: {
              focus: 'series'
            },
            data: [820, 832, 901, 934, 1290, 1330, 1320]
          }
        ]
      });
      let chart4 = echarts.init(document.getElementById('chart4'))
      // 绘制图表
      chart4.setOption({
        xAxis: {
          type: 'category',
          data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
        },
        yAxis: {
          type: 'value'
        },


        color: '#54f6c1', // 折线点的颜色
        lineStyle: {
          color: '#41ff0d' // 折线的颜色
        },
        series: [{
          data: [820, 932, 901, 934, 1290, 1330, 1320],
          type: 'line',
          smooth: true
        }]
      });
      let chart5 = echarts.init(document.getElementById('chart5'))
      // 绘制图表
      chart5.setOption({
        color : [ '#3AA1FF', '#36CBCB', '#4ECB73', '#FBD437' ],
        tooltip: {
          trigger: 'item'
        },
        legend: {
          top: '5%',
          left: 'left',
          orient:'vertical'
        },
        series: [
          {

            name: '访问来源',
            type: 'pie',
            radius: ['50%', '70%'],
            avoidLabelOverlap: false,
            label: {
              show: false,
              position: 'center',
              normal : {
                //饼形图显示格式
                formatter : '{b|{b}}  {per|{d}%}  ',
                rich : {
                  b : {
                    color : '#00B4FB',       //字体颜色
                    fontSize : 14,
                    lineHeight : 33
                  },
                  //设置百分比数字颜色
                  per : {
                    color : '#00B4FB',
                    fontSize : 14,
                    padding : [ 2, 4 ],
                    borderRadius : 2
                  }
                }
              }
            },
            itemStyle:{
              borderWidth:3,
              borderColor:'#fff',
            },
            emphasis: {
              label: {
                show: true,
                fontSize: '40',
                fontWeight: 'bold'
              }
            },
            labelLine: {
              show: true,
              length: 35,
              length2: 10,
            },
            data: [
              {value: 1048, name: '搜索引擎'},
              {value: 735, name: '直接访问'},
              {value: 580, name: '邮件营销'},
              {value: 484, name: '联盟广告'},
              {value: 300, name: '视频广告'}
            ]
          }
        ]

      });

    }
  }

}

</script>
<style>
@import "../css/weather.css";
</style>
