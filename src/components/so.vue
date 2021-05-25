<template>
  <div class="row">
    <div class="col-md-6">
      <h3 class="h3">今日各市气温</h3>
      <div id="myChart" :style="{width: '800px', height: '350px'}"></div>
    </div>
    <div class="col-md-6">
      <h3 class="h3">本月各市晴天数</h3>
      <div id="chart7" :style="{width: '800px', height: '350px'}"></div>
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
      }
      );

      let chart7 = echarts.init(document.getElementById('chart7'))
      // 绘制图表
      chart7.setOption({
        tooltip: {
          trigger: 'item',
          formatter: '{a} <br/>{b} : {c} ({d}%)'
        },
        legend: {
          bottom: 10,
          left: 'center',
          data: ['西凉', '益州', '兖州', '荆州', '幽州']
        },
        series: [
          {
            type: 'pie',
            radius: '65%',
            center: ['50%', '50%'],
            selectedMode: 'single',
            data: [
              {
                value: 1548,
                name: '幽州',
                label: {
                  formatter: [
                    '{title|{b}}{abg|}',
                    '  {weatherHead|天气}{valueHead|天数}{rateHead|占比}',
                    '{hr|}',
                    '  {Sunny|}{value|202}{rate|55.3%}',
                    '  {Cloudy|}{value|142}{rate|38.9%}',
                    '  {Showers|}{value|21}{rate|5.8%}'
                  ].join('\n'),
                  backgroundColor: '#eee',
                  borderColor: '#777',
                  borderWidth: 1,
                  borderRadius: 4,
                  rich: {
                    title: {
                      color: '#eee',
                      align: 'center'
                    },
                    abg: {
                      backgroundColor: '#333',
                      width: '100%',
                      align: 'right',
                      height: 25,
                      borderRadius: [4, 4, 0, 0]
                    },
                    // Sunny: {
                    //   height: 30,
                    //   align: 'left',
                    //   backgroundColor: {
                    //     image: weatherIcons.Sunny
                    //   }
                    // },
                    // Cloudy: {
                    //   height: 30,
                    //   align: 'left',
                    //   backgroundColor: {
                    //     image: weatherIcons.Cloudy
                    //   }
                    // },
                    // Showers: {
                    //   height: 30,
                    //   align: 'left',
                    //   backgroundColor: {
                    //     image: weatherIcons.Showers
                    //   }
                    // },
                    weatherHead: {
                      color: '#333',
                      height: 24,
                      align: 'left'
                    },
                    hr: {
                      borderColor: '#777',
                      width: '100%',
                      borderWidth: 0.5,
                      height: 0
                    },
                    value: {
                      width: 20,
                      padding: [0, 20, 0, 30],
                      align: 'left'
                    },
                    valueHead: {
                      color: '#333',
                      width: 20,
                      padding: [0, 20, 0, 30],
                      align: 'center'
                    },
                    rate: {
                      width: 40,
                      align: 'right',
                      padding: [0, 10, 0, 0]
                    },
                    rateHead: {
                      color: '#333',
                      width: 40,
                      align: 'center',
                      padding: [0, 10, 0, 0]
                    }
                  }
                }
              },
              {value: 735, name: '荆州'},
              {value: 510, name: '兖州'},
              {value: 434, name: '益州'},
              {value: 335, name: '西凉'}
            ],
            emphasis: {
              itemStyle: {
                shadowBlur: 10,
                shadowOffsetX: 0,
                shadowColor: 'rgba(0, 0, 0, 0.5)'
              }
            }
          }
          ]}
      );
    }
  }
}

</script>

<style>
@import "../css/so.css";
</style>