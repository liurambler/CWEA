<template>
  <div :class='className' :style='{height:height,width:width}' />
</template>

<script>
import echarts from 'echarts'
require('echarts/lib/chart/map')
require('echarts/map/js/china')
require('echarts/theme/macarons') // echarts theme
import resize from './mixins/resize'

export default {
  mixins: [resize],
  props: {
    className: {
      type: String,
      default: 'chart'
    },
    width: {
      type: String,
      default: '100%'
    },
    height: {
      type: String,
      default: '400px'
    },
    autoResize: {
      type: Boolean,
      default: true
    },
    chartData: {
      type: Object,
      required: false
    }
  },
  data() {
    return {
      chart: null
    }
  },
  mounted() {
    this.$nextTick(() => {
      this.initChart()
    })
  },
  beforeDestroy() {
    if (!this.chart) {
      return
    }
    this.chart.dispose()
    this.chart = null
  },
  methods: {
    initChart() {
      this.chart = echarts.init(this.$el, 'macarons')
      this.chart.setOption({
        baseOption: {
          timeline: {
            data: ['2002-01-01', '2003-01-01', '2004-01-01']
          },
          title: {
            text: '风电装机市场力指数',
            subtext: 'CWEA',
            left: 'center'

          },
          tooltip : {
            trigger: 'item',
            formatter: '{b} : {c}'
          },
          dataRange: {
            orient: 'vertical',
            min: 0,
            max: 10000,
            text: ['10000', '0'], // 文本，默认为数值文本
            splitNumber: 0
          },
          series: [
            {
              type: 'map',
              mapType: 'china',
              selectedMode : 'multiple',
              itemStyle: {
                normal: { 
                  label: { show: false },
                  borderColor: '#fff',
                  },
                emphasis: { 
                  label: { show: true },
                  borderColor: '#ddd',
                  }
              },
            }
          ]
        },
        options: [
          {
            title: {
              subtext: '2011'
            },
            series: [
              {
                data: [{
                  name: '\u65b0\u7586',
                  value: 1021
                }, {
                  name: '\u5409\u6797',
                  value: 1108
                }, {
                  name: '\u5185\u8499\u53e4',
                  value: 1287
                }, {
                  name: '\u5b81\u590f',
                  value: 1641
                }, {
                  name: '\u9ed1\u9f99\u6c5f',
                  value: 1711
                }, {
                  name: '\u8fbd\u5b81',
                  value: 1751
                }, {
                  name: '\u7518\u8083',
                  value: 2004
                }, {
                  name: '\u6cb3\u5317',
                  value: 2007
                }, {
                  name: '\u5c71\u4e1c',
                  value: 2370
                }, {
                  name: '\u5e7f\u4e1c',
                  value: 2512
                }, {
                  name: '\u6cb3\u5357',
                  value: 2656
                }, {
                  name: '\u9655\u897f',
                  value: 2688
                }, {
                  name: '\u4e91\u5357',
                  value: 2710
                }, {
                  name: '\u5c71\u897f',
                  value: 3375
                }, {
                  name: '\u798f\u5efa',
                  value: 3752
                }, {
                  name: '\u6c5f\u82cf',
                  value: 5102
                }, {
                  name: '\u6e56\u5317',
                  value: 6851
                }, {
                  name: '\u4e0a\u6d77',
                  value: 7087
                }, {
                  name: '\u6d59\u6c5f',
                  value: 7126
                }, {
                  name: '\u6e56\u5357',
                  value: 7644
                }, {
                  name: '\u9752\u6d77',
                  value: 8071
                }, {
                  name: '\u8d35\u5dde',
                  value: 9516
                }, {
                  name: '\u5929\u6d25',
                  value: 10000
                }, {
                  name: '\u5317\u4eac',
                  value: 10000
                }, {
                  name: '\u6c5f\u897f',
                  value: 10000
                }, {
                  name: '\u56db\u5ddd',
                  value: 10000
                }, {
                  name: '\u5b89\u5fbd',
                  value: 10000
                }, {
                  name: '\u5e7f\u897f',
                  value: 10000
                }]
                }
            ]
          },
          {
            title: {
              subtext: '2012'
            },
            series: [
              {
                data: [{
                  name: '\u65b0\u7586',
                  value: 1066
                }, {
                  name: '\u7518\u8083',
                  value: 1077
                }, {
                  name: '\u8fbd\u5b81',
                  value: 1153
                }, {
                  name: '\u9ed1\u9f99\u6c5f',
                  value: 1286
                }, {
                  name: '\u5185\u8499\u53e4',
                  value: 1367
                }, {
                  name: '\u5b81\u590f',
                  value: 1564
                }, {
                  name: '\u5e7f\u4e1c',
                  value: 1773
                }, {
                  name: '\u6cb3\u5317',
                  value: 1777
                }, {
                  name: '\u4e91\u5357',
                  value: 2104
                }, {
                  name: '\u5409\u6797',
                  value: 2149
                }, {
                  name: '\u6cb3\u5357',
                  value: 2285
                }, {
                  name: '\u798f\u5efa',
                  value: 2624
                }, {
                  name: '\u5c71\u897f',
                  value: 2762
                }, {
                  name: '\u5c71\u4e1c',
                  value: 2959
                }, {
                  name: '\u8d35\u5dde',
                  value: 3474
                }, {
                  name: '\u5e7f\u897f',
                  value: 3581
                }, {
                  name: '\u9752\u6d77',
                  value: 3899
                }, {
                  name: '\u6d59\u6c5f',
                  value: 4702
                }, {
                  name: '\u9655\u897f',
                  value: 4839
                }, {
                  name: '\u91cd\u5e86',
                  value: 5061
                }, {
                  name: '\u6c5f\u897f',
                  value: 5102
                }, {
                  name: '\u6c5f\u82cf',
                  value: 5712
                }, {
                  name: '\u6e56\u5357',
                  value: 5917
                }, {
                  name: '\u5b89\u5fbd',
                  value: 6314
                }, {
                  name: '\u4e0a\u6d77',
                  value: 7923
                }, {
                  name: '\u5929\u6d25',
                  value: 10000
                }, {
                  name: '\u6e56\u5317',
                  value: 10000
                }, {
                  name: '\u56db\u5ddd',
                  value: 10000
                }, {
                  name: '\u6d77\u5357',
                  value: 10000
                }]
              }
            ]
          },
          {
            title: {
              subtext: '2013'
            },
            series: [
              {
                data: [{
                  name: '\u65b0\u7586',
                  value: 734.
                }, {
                  name: '\u8fbd\u5b81',
                  value: 1175
                }, {
                  name: '\u5b81\u590f',
                  value: 1260
                }, {
                  name: '\u5e7f\u4e1c',
                  value: 1285
                }, {
                  name: '\u5c71\u897f',
                  value: 1312
                }, {
                  name: '\u4e91\u5357',
                  value: 1422
                }, {
                  name: '\u5c71\u4e1c',
                  value: 1445
                }, {
                  name: '\u9ed1\u9f99\u6c5f',
                  value: 1573
                }, {
                  name: '\u7518\u8083',
                  value: 1605
                }, {
                  name: '\u6e56\u5357',
                  value: 1688
                }, {
                  name: '\u5185\u8499\u53e4',
                  value: 1873
                }, {
                  name: '\u6cb3\u5317',
                  value: 1975
                }, {
                  name: '\u6e56\u5317',
                  value: 2034
                }, {
                  name: '\u6d59\u6c5f',
                  value: 2451
                }, {
                  name: '\u9752\u6d77',
                  value: 2513
                }, {
                  name: '\u5409\u6797',
                  value: 2567
                }, {
                  name: '\u8d35\u5dde',
                  value: 2672
                }, {
                  name: '\u6c5f\u82cf',
                  value: 2774
                }, {
                  name: '\u9655\u897f',
                  value: 2783
                }, {
                  name: '\u798f\u5efa',
                  value: 2863
                }, {
                  name: '\u6cb3\u5357',
                  value: 3359
                }, {
                  name: '\u56db\u5ddd',
                  value: 3510
                }, {
                  name: '\u5e7f\u897f',
                  value: 4659
                }, {
                  name: '\u5b89\u5fbd',
                  value: 5510
                }, {
                  name: '\u91cd\u5e86',
                  value: 8423
                }, {
                  name: '\u5929\u6d25',
                  value: 10000
                }, {
                  name: '\u5317\u4eac',
                  value: 10000
                }, {
                  name: '\u6c5f\u897f',
                  value: 10000
                }, {
                  name: '\u4e0a\u6d77',
                  value: 10000
                }, {
                  name: '\u897f\u85cf',
                  value: 10000
                }]
              }
            ]
          }
        ]
      })
    }
  }
}
</script>
