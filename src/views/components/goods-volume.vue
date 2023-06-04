<template>
  <div class="goods-volume">
    <Box title="商品交易量">
      <template slot="prefix">
        <div class="btns">
          <span :class="{ active: active === 1 }" @click="active = 1"
            >交易额（亿元）</span
          >
          <span :class="{ active: active === 2 }" @click="active = 2"
            >交易重量（万吨）</span
          >
        </div>
      </template>
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
      active: 1,
      chart: null
    }
  },

  watch: {
    active () {
      this.initChart()
    }
  },

  mounted () {
    this.$nextTick(() => {
      this.initChart()
    })
  },

  methods: {
    initChart () {
      let options = {}

      if (this.active === 1) {
        options = {
          轻废: 229.01,
          中废: 372.12,
          重废: 0.36,
          剪切料: 0.13,
          破碎料: 4.33,
          废铝: 2.25,
          废玻璃: 0.57
        }
      } else {
        options = {
          轻废: 746.1,
          中废: 0.1,
          重废: 1.16,
          剪切料: 0.39,
          破碎料: 11.68,
          废铝: 1.46,
          废玻璃: 6.7
        }
      }

      const results = []

      for (const key in options) {
        if (Object.hasOwnProperty.call(options, key)) {
          const element = options[key]
          results.push({
            value: element,
            name: key
          })
        }
      }

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
        tooltip: {
          show: true
        },
        legend: {
          show: true,
          top: 'center',
          right: 10,
          orient: 'vertical',
          itemWidth: 16,
          itemHeight: 4,
          borderRadius: 2,
          itemGap: 13,
          textStyle: {
            color: 'rgba(255, 255, 255, 1)',
            rich: {
              a: {
                width: 55,
                fontSize: 14,
                padding: [0, 0, 0, 10]
              },
              b: {
                color: 'rgba(49, 147, 248, 1)',
                fontSize: 14
              }
            }
          },
          // 使用回调函数
          formatter: (name) => {
            return `{a|${name}}` + `{b|${options[name]}}`
          }
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
            center: ['30%', '50%'],
            // roseType: 'area',
            zlevel: 10,
            label: {
              show: false
            },
            itemStyle: {
              normal: {
                color: function (params) {
                  const colorList = [
                    {
                      c1: ' #0176D3',
                      c2: '#13B7FF'
                    },
                    {
                      c1: ' #45EAFF',
                      c2: '#40ADAC'
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
                      c1: '#c5223b',
                      c2: '#fa768a'
                    },
                    {
                      c1: '#12B3F8',
                      c2: '#7DE8FF'
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
            data: results
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

  .btns {
    display: flex;
    align-items: center;
    justify-content: flex-end;

    span {
      font-size: 12px;
      font-family: Microsoft YaHei;
      font-weight: 400;
      color: #3193f8;
      padding: 2px 6px;
      background: rgba(10, 116, 241, 0.24);
      border-radius: 2px;
      margin-left: 6px;
      cursor: pointer;
    }

    .active {
      background: rgba(10, 116, 241, 0.36);
      border: 1px solid #0a74f1;
      border-radius: 2px;
      font-size: 12px;
      font-family: Microsoft YaHei;
      font-weight: 400;
      color: #ffffff;
    }
  }

  .chart {
    width: 100%;
    height: 100%;
  }
}
</style>
