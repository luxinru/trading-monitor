<template>
  <div class="customer-volume">
    <Box title="客户交易量" backgroundDirection="right">
      <div ref="chart" class="chart"></div>
    </Box>
  </div>
</template>

<script>
import * as echarts from 'echarts'
import Box from '@/components/box.vue'

export default {
  name: 'CustomerVolume',

  components: {
    Box
  },

  data () {
    return {
      intervalId: null,
      chart: null,
      index: 0,
      sourcelist: [
        { name: '唐山正丰钢', value: 301562.47 },
        { name: '唐山成益实', value: 40389.23 },
        { name: '安徽林洪重工科', value: 26185.2 },
        { name: '南京图祺再生资', value: 20577.08 },
        { name: '兰鑫钢铁集', value: 20330.18 },
        { name: '河北敬业集', value: 16349.59 },
        { name: '兖矿国际贸易（山东）', value: 14589.22 },
        { name: '山西省黎城县通鑫再生资源回收利', value: 13889.21 },
        { name: '中铁物轨道科技服务集', value: 13745.46 },
        { name: '山东磐金锻造机', value: 13350.43 },
        { name: '安徽碧深高', value: 12295.76 },
        { name: '宁夏共享商', value: 11949.9 },
        { name: '郑州永通特', value: 11937.74 },
        { name: '河钢股份有限公司（承德）', value: 11864.48 },
        { name: '滨州新格有色金', value: 11825.97 },
        { name: '芜湖新兴铸', value: 11111.65 },
        { name: '山西晋钢智造科技实', value: 10630.37 },
        { name: '宁夏钢铁（集团）', value: 10612.37 },
        { name: '沙钢集团安阳永兴特', value: 10611.89 },
        { name: '郎溪县盛强园艺钢制', value: 10265.84 },
        { name: '郎溪县华新机械配件制', value: 9685.78 },
        { name: '闽源钢铁集', value: 9680.69 },
        { name: '内蒙古包钢钢联股', value: 8850.06 },
        { name: '上海梅山钢铁股', value: 8075.29 },
        { name: '江苏南钢环宇贸', value: 7927.28 },
        { name: '云南曲靖钢铁集团凤凰钢', value: 7158.62 },
        { name: '郎溪县昌盛钢结构材', value: 6769.26 },
        { name: '金环集团河北供应链管', value: 5664.16 },
        { name: '河源德润钢', value: 5611.66 },
        { name: '乌兰浩特钢', value: 5609.76 },
        { name: '河北容基物流投', value: 5564.24 },
        { name: '山西宝隆科', value: 5280.77 },
        { name: '山西通才工', value: 4880.59 },
        { name: '安徽亚鑫重工铸', value: 4805.05 },
        { name: '郎溪县宏嘉新材料科', value: 4758.68 },
        { name: '宁夏建龙龙祥钢', value: 4579.66 },
        { name: '巩义新格有色金', value: 4512.56 },
        { name: '敬业钢', value: 4440.69 },
        { name: '鼎业再生资源回收利', value: 4382.29 },
        { name: '山东鲁丽钢', value: 4337.49 },
        { name: '唐山市丰润区城乡鑫业再生资', value: 4208.03 },
        { name: '介休市永焱废弃资源综合利', value: 4006.28 },
        { name: '宝山钢铁股', value: 3710.17 },
        { name: '山西华翔集团股', value: 3635.9 },
        { name: '襄汾县星原钢铁集', value: 3497.08 },
        { name: '扬州市秦邮特种金属材', value: 3271.45 },
        { name: '宁夏兴华钢', value: 3250.16 },
        { name: '陕西华鑫特种钢铁集', value: 3141.48 },
        { name: '乌海沃仑机械加', value: 2980.49 },
        { name: '兴安盟敬业再生资', value: 2976.45 }
      ],
      list: []
    }
  },

  mounted () {
    this.$nextTick(() => {
      this.sourcelist.forEach((item, index) => {
        item.index = index + 1
      })
      this.list = this.sourcelist.slice(this.index, this.index + 6)
      this.initChart()
      this.intervalId = setInterval(() => {
        this.index += 1

        if (this.index + 6 > this.sourcelist.length) {
          this.index = 0
          echarts.dispose(this.$refs.chart)
        }

        this.list = this.sourcelist.slice(this.index, this.index + 6)
        this.initChart()
      }, 5 * 1000)
    })
  },

  beforeDestroy () {
    window.clearInterval(this.intervalId)
  },

  methods: {
    initChart () {
      // 基于准备好的dom，初始化echarts实例
      this.chart = echarts.init(this.$refs.chart)

      var colorList = ['#f36c6c', '#e6cf4e', '#20d180', '#0093ff']
      var datas = this.list

      const option = {
        tooltip: {
          trigger: 'axis',
          axisPointer: {
            type: 'shadow'
          }
        },
        legend: {
          show: false
        },
        grid: {
          left: 0,
          right: '2%',
          top: '5%',
          bottom: 0,
          containLabel: true
        },
        xAxis: {
          show: false,
          type: 'value'
        },
        yAxis: [
          {
            type: 'category',
            inverse: true,
            axisLine: {
              show: false
            },
            axisTick: {
              show: false
            },
            axisPointer: {
              label: {
                show: true,
                margin: 30
              }
            },
            data: datas.map((item) => item.name),
            axisLabel: {
              margin: 50,
              fontSize: 14,
              align: 'left',
              color: 'rgba(238, 238, 238, 0.7',
              rich: {
                b: {
                  color: '#fff',
                  backgroundColor: colorList[3],
                  width: 30,
                  height: 30,
                  align: 'center',
                  borderRadius: 2
                }
              },
              formatter: function (params) {
                const finded = datas.find(item => item.name === params)
                return ['{b|' + finded.index + '}'].join('\n')
              }
            }
          },
          {
            type: 'category',
            inverse: true,
            axisTick: 'none',
            axisLine: 'none',
            show: true,
            data: datas.map((item) => item.value),
            axisLabel: {
              show: true,
              fontSize: 14,
              color: 'rgba(238, 238, 238, 0.7)',
              formatter: '{value}'
            }
          }
        ],
        series: [
          {
            z: 2,
            name: 'value',
            type: 'bar',
            barCategoryGap: '40%',
            barGap: '20%',
            barWidth: 12,
            data: datas.map((item, i) => {
              var itemStyle = {
                color: colorList[3],
                barBorderRadius: [10, 10, 10, 10]
              }
              return {
                value: item.value,
                itemStyle: itemStyle
              }
            }),
            label: {
              normal: {
                color: 'rgba(238, 238, 238, 0.7)',
                show: true,
                position: [0, '-20px'],
                textStyle: {
                  fontSize: 14
                },
                formatter: function (a, b) {
                  return a.name
                }
              }
            }
          }
        ]
      }

      // 绘制图表
      this.chart.setOption(option)
    }
  }
}
</script>

<style lang="scss" scoped>
.customer-volume {
  width: 100%;
  height: 100%;
  overflow: hidden;

  .chart {
    width: 100%;
    height: 100%;
  }
}
</style>
