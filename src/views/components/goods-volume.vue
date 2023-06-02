<template>
  <div class="goods-volume">
    <Box title="商品交易量">
      <div class="chart" ref="chart"></div>
    </Box>
  </div>
</template>

<script>
import * as echarts from 'echarts'
import Box from '@/components/box.vue'

export default {
  name: 'GoodsVolume',

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
          left: 0,
          top: 0,
          bottom: 0,
          right: 0,
          containLabel: true
        },
        polar: {},
        angleAxis: {
          axisLine: {
            show: false
          },
          axisLabel: {
            show: false
          }
        },
        radiusAxis: {
          axisLine: {
            show: false
          },
          axisLabel: {
            show: false
          },
          splitLine: {
            lineStyle: {
              width: 0
            }
          }
        },
        calculable: true,
        series: [
          {
            stack: 'a',
            type: 'pie',
            radius: ['20%', '80%'],
            roseType: 'area',
            zlevel: 10,
            label: {
              show: false
            },
            itemStyle: {
              normal: {
                color: function (params) {
                  const colorList = [
                    {
                      c1: '#c5223b',
                      c2: '#fa768a'
                    },
                    {
                      c1: ' #de7110',
                      c2: '#fecd70'
                    },
                    {
                      c1: '#d09f08',
                      c2: '#FFD145'
                    },
                    {
                      c1: '#238483',
                      c2: '#55C27C'
                    },
                    {
                      c1: ' #45EAFF',
                      c2: '#40ADAC'
                    },
                    {
                      c1: '#12B3F8',
                      c2: '#7DE8FF'
                    },
                    {
                      c1: ' #0176D3',
                      c2: '#13B7FF'
                    },
                    {
                      c1: '#015BD3',
                      c2: '#138DFF'
                    },
                    {
                      c1: ' #7c94e7',
                      c2: '#1e2783'
                    }
                  ]
                  return new echarts.graphic.LinearGradient(1, 0, 0, 0, [
                    {
                      offset: 0,
                      color: colorList[params.dataIndex].c1
                    },
                    {
                      offset: 1,
                      color: colorList[params.dataIndex].c2
                    }
                  ])
                }
              }
            },
            data: [
              {
                value: 1313,
                name: '其他'
              },
              {
                value: 1750,
                name: '技术类文档'
              },
              {
                value: 1750,
                name: '图书资料目录'
              },
              {
                value: 1969,
                name: '发文目录'
              },
              {
                value: 2188,
                name: '户籍档案'
              },
              {
                value: 2626,
                name: '专业（业务）档案'
              },
              {
                value: 3063,
                name: '旧文书档案'
              }
            ]
          }
        ]
      })
    }
  }
}
</script>

<style lang="scss" scoped>
.goods-volume {
  width: 100%;
  height: 100%;

  .chart {
    width: 100%;
    height: 100%;
  }
}
</style>
