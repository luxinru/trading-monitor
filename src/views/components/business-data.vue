<template>
  <div class="business-data">
    <Box title="经营数据">
      <div class="chart" ref="chart"></div>
    </Box>
  </div>
</template>

<script>
import * as echarts from 'echarts'
import Box from '@/components/box.vue'

export default {
  name: 'BusinessData',

  components: {
    Box
  },

  data () {
    return {
      chart: null
    }
  },

  mounted () {
    this.$nextTick(() => {
      this.initChart()
    })
  },

  methods: {
    initChart () {
      // 基于准备好的dom，初始化echarts实例
      this.chart = echarts.init(this.$refs.chart)
      // 绘制图表
      this.chart.setOption({
        grid: {
          top: '15%',
          left: '0',
          right: '5%',
          bottom: '0',
          containLabel: true
        },
        tooltip: {
          trigger: 'axis',
          formatter (params) {
            const val0 = params[0].value
            const val1 = params[1].value
            const circle =
              '<span style="display:inline-block;margin-right:5px;border-radius:50%;width:10px;height:10px;left:5px;background-color:'
            const data0 = `${circle}rgba(49, 147, 248, 1)"></span> ${params[0].seriesName}: ${val0}`
            const data1 = `${circle}rgba(55, 255, 201, 1)"></span> ${params[1].seriesName}: ${val1}`
            return `${params[0].axisValueLabel}<br/>${data0}<br/>${data1}`
          }
        },
        legend: {
          left: 'center',
          top: 0,
          icon: 'rect',
          itemWidth: 18,
          itemHeight: 2,
          itemGap: 15,
          textStyle: {
            color: 'rgba(255, 255, 255, 1)',
            fontFamily: 'Source Han Sans CN',
            fontSize: 15,
            fontWeight: 400
          },

          data: [
            {
              name: '交易额(万元)',
              itemStyle: {
                color: 'rgba(49, 147, 248, 1)'
              }
            },
            {
              name: '交易吨数(万吨)',
              itemStyle: {
                color: 'rgba(55, 255, 201, 1)'
              }
            }
          ]
        },
        xAxis: {
          type: 'category',
          data: [
            '中再宁夏',
            '中再洛阳',
            '中再山西',
            '中再常州',
            '中再睢县',
            '安徽回收',
            '安徽开发',
            '滨州新格',
            '巩义新格'
          ],
          axisLine: {
            show: false
          },
          axisTick: {
            show: false
          },
          axisLabel: {
            show: true,
            interval: 0,
            rotate: 30,
            textStyle: {
              color: 'rgba(238, 238, 238, 0.7)',
              fontSize: 12
            }
          }
        },
        yAxis: [
          {
            type: 'value',
            axisLine: {
              show: false
            },
            axisTick: {
              show: false
            },
            axisLabel: {
              color: 'rgba(238, 238, 238, 0.7)',
              fontSize: 12
            },
            splitLine: {
              show: true,
              lineStyle: {
                color: 'rgba(183, 200, 235, 0.15)',
                type: 'dashed'
              }
            }
          },
          {
            type: 'value',
            axisLine: {
              show: false
            },
            axisTick: {
              show: false
            },
            axisLabel: {
              color: 'rgba(238, 238, 238, 0.7)',
              fontSize: 12
            },
            splitLine: {
              show: true,
              lineStyle: {
                color: 'rgba(183, 200, 235, 0.15)',
                type: 'dashed'
              }
            }
          }
        ],
        series: [
          {
            name: '交易额(万元)',
            type: 'line',
            // showAllSymbol: true, //显示所有图形。
            symbol: 'circle', // 标记的图形为实心圆
            symbolSize: 6, // 标记的大小
            itemStyle: {
              // 折线拐点标志的样式
              color: 'rgba(0, 0, 0, 1)',
              borderWidth: '2',
              borderColor: 'rgba(49, 147, 248, 1)'
            },
            lineStyle: {
              color: 'rgba(49, 147, 248, 1)'
            },
            data: [
              546300.0, 25210.0, 24200.0, 17100.0, 10600.0, 44800.0, 126300.0,
              11800.0, 4500.0
            ]
          },
          {
            name: '交易吨数(万吨)',
            type: 'line',
            yAxisIndex: 1,
            showAllSymbol: true, // 显示所有图形。
            symbol: 'circle', // 标记的图形为实心圆
            symbolSize: 6, // 标记的大小
            itemStyle: {
              // 折线拐点标志的样式
              color: 'rgba(0, 0, 0, 1)',
              borderWidth: '2',
              borderColor: 'rgba(55, 255, 201, 1)'
            },
            lineStyle: {
              color: 'rgba(55, 255, 201, 1)'
            },
            data: [174.18, 8.32, 7.61, 10.46, 3.28, 13.23, 38.23, 0.79, 0.31]
          }
        ]
      })
    }
  }
}
</script>

<style lang="scss" scoped>
.business-data {
  width: 100%;
  height: 100%;

  .chart {
    width: 100%;
    height: 100%;
  }
}
</style>
