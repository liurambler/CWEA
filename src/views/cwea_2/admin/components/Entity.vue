<template>
  <div :class="className" :style="{height:height,width:width}" />
</template>

<script>
import echarts from 'echarts'
require('echarts/theme/macarons') // echarts theme
import resize from './mixins/resize'

const animationDuration = 6000

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
      default: '800px'
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

      var builderJson = {
        'all': 10000,
        'charts': {
          '\u5f00\u53d1\u55461': 1442.0230333984932,
          '\u5f00\u53d1\u55464': 1490.4510804006427,
          '\u5f00\u53d1\u55467': 1519.9206495453502,
          '\u5f00\u53d1\u554613': 2613.2303609080254,
          '\u5f00\u53d1\u554611': 2727.6410701241784,
          '\u5f00\u53d1\u554616': 2951.0275754422464,
          '\u5f00\u53d1\u55462': 3234.434517158651,
          '\u5f00\u53d1\u554664': 3333.408405026801,
          '\u5f00\u53d1\u55466': 3399.1825213933134,
          '\u5f00\u53d1\u55468': 3819.1397546142584,
          '\u5f00\u53d1\u554612': 4753.1877288221185,
          '\u6837\u673a': 4978.852352924939,
          '\u5f00\u53d1\u554610': 4989.573183209758,
          '\u5f00\u53d1\u554638': 5004.591368227732,
          '\u5f00\u53d1\u554658': 5008.0,
          '\u5f00\u53d1\u55465': 5017.301038062284,
          '\u5f00\u53d1\u554657': 5132.504056246621,
          '\u5f00\u53d1\u55469': 5363.361111073641,
          '\u5f00\u53d1\u554636': 5555.555555555556,
          '\u5f00\u53d1\u554614': 5603.356735349121,
          '\u5f00\u53d1\u554622': 7009.850314847907,
          '\u5f00\u53d1\u554665': 8906.122448979591,
          '\u5f00\u53d1\u554646': 10000.0,
          '\u5f00\u53d1\u554659': 10000.0,
          '\u5f00\u53d1\u554666': 10000.0,
          '\u5f00\u53d1\u554692': 10000.0,
          '\u5f00\u53d1\u554689': 10000.0,
          '\u5f00\u53d1\u554690': 10000.0,
          '\u5f00\u53d1\u554683': 10000.0,
          '\u5f00\u53d1\u554631': 10000.0,
          '\u5f00\u53d1\u554662': 10000.0,
          '\u5f00\u53d1\u554623': 10000.0,
          '\u5f00\u53d1\u554663': 10000.0,
          '\u5f00\u53d1\u554650': 10000.0,
          '\u5f00\u53d1\u554656': 10000.0,
          '\u5f00\u53d1\u554686': 10000.0,
          '\u5f00\u53d1\u554681': 10000.0,
          '\u5f00\u53d1\u554632': 10000.0,
          '\u5f00\u53d1\u554652': 10000.0,
          '\u5f00\u53d1\u55463': 10000.0,
          '\u5f00\u53d1\u554651': 10000.0,
          '\u5f00\u53d1\u554627': 10000.0,
          '\u5f00\u53d1\u554673': 10000.0,
          '\u5f00\u53d1\u5546120': 10000.0,
          '\u5f00\u53d1\u554630': 10000.0,
          '\u5f00\u53d1\u554661': 10000.0,
          '\u5f00\u53d1\u554682': 10000.0,
          '\u5f00\u53d1\u554677': 10000.0,
          '\u5f00\u53d1\u554635': 10000.0,
          '\u5f00\u53d1\u554676': 10000.0,
          '\u5f00\u53d1\u554634': 10000.0,
          '\u5f00\u53d1\u554637': 10000.0,
          '\u5f00\u53d1\u554685': 10000.0,
          '\u5f00\u53d1\u554625': 10000.0,
          '\u5f00\u53d1\u554691': 10000.0,
          '\u5f00\u53d1\u554669': 10000.0,
          '\u5f00\u53d1\u554687': 10000.0,
          '\u5f00\u53d1\u554619': 10000.0
        },
        'components': {
          '\u5236\u9020\u4f01\u4e1a1': 907.9475308641978,
          '\u5236\u9020\u4f01\u4e1a10': 1519.6016402937767,
          '\u5236\u9020\u4f01\u4e1a19': 1645.1446280991738,
          '\u5236\u9020\u4f01\u4e1a11': 1718.3999999999999,
          '\u5236\u9020\u4f01\u4e1a5': 1744.5406205966558,
          '\u5236\u9020\u4f01\u4e1a4': 2026.2705734575131,
          '\u5236\u9020\u4f01\u4e1a13': 2283.8897898061005,
          '\u5236\u9020\u4f01\u4e1a6': 2391.2225317419134,
          '\u5236\u9020\u4f01\u4e1a18': 2439.8887024234077,
          '\u5236\u9020\u4f01\u4e1a14': 2707.84,
          '\u5236\u9020\u4f01\u4e1a7': 2738.2295130537627,
          '\u5236\u9020\u4f01\u4e1a3': 3452.210580494085,
          '\u5236\u9020\u4f01\u4e1a17': 4219.770648860502,
          '\u5236\u9020\u4f01\u4e1a26': 5007.801660608314,
          '\u5236\u9020\u4f01\u4e1a15': 5069.322790338118,
          '\u5236\u9020\u4f01\u4e1a16': 5460.815829718173,
          '\u5236\u9020\u4f01\u4e1a29': 5484.408578571115,
          '\u5236\u9020\u4f01\u4e1a2': 6165.279429250892,
          '\u5236\u9020\u4f01\u4e1a12': 6173.127229488703,
          '\u5236\u9020\u4f01\u4e1a8': 6957.5580418880745,
          '\u5236\u9020\u4f01\u4e1a23': 10000.0,
          '\u5236\u9020\u4f01\u4e1a25': 10000.0,
          '\u5236\u9020\u4f01\u4e1a28': 10000.0,
          '\u5236\u9020\u4f01\u4e1a30': 10000.0,
          '\u5236\u9020\u4f01\u4e1a9': 10000.0,
          '\u5236\u9020\u4f01\u4e1a31': 10000.0,
          '\u5236\u9020\u4f01\u4e1a22': 10000.0
        }
      }

      var downloadJson = {

        '开发商1': 7630,
        '开发商4': 4241,
        '开发商9': 3072,
        '开发商7': 1643,
        '开发商8': 1472,
        '其他': 9630
      }

      var themeJson = {
        '制造企业1': 4853.5,
        '制造企业3': 4604,
        '制造企业10': 3515,
        '制造企业19': 1852,
        '制造企业23': 1416,
        '其他': 11450
      }

      const option = {
        tooltip: {},
        sort: 'ascending',
        title: [{
          text: '市场集中度指数',
          subtext: '数值越高，代表其客户关系越单一',
          x: '25%',
          textAlign: 'center'
        }, {
          text: '开发商占有率',
          subtext: '总计 ' + Object.keys(downloadJson).reduce(function(all, key) {
            return all + downloadJson[key]
          }, 0),
          x: '75%',
          textAlign: 'center'
        }, {
          text: '制造企业占有率',
          subtext: '总计 ' + Object.keys(themeJson).reduce(function(all, key) {
            return all + themeJson[key]
          }, 0),
          x: '75%',
          y: '50%',
          textAlign: 'center'
        }],
        grid: [{
          top: 50,
          width: '50%',
          bottom: '45%',
          left: 10,
          containLabel: true
        }, {
          top: '55%',
          width: '50%',
          bottom: 0,
          left: 10,
          containLabel: true
        }],
        xAxis: [{
          type: 'value',
          max: builderJson.all,
          splitLine: {
            show: false
          }
        }, {
          type: 'value',
          max: builderJson.all,
          gridIndex: 1,
          splitLine: {
            show: false
          }
        }],
        yAxis: [{
          type: 'category',
          data: Object.keys(builderJson.charts),
          axisLabel: {
            interval: 0,
            rotate: 30,
            fontSize: 8,
            interval: 1
          },
          splitLine: {
            show: false
          }
        }, {
          gridIndex: 1,
          type: 'category',
          data: Object.keys(builderJson.components),
          axisLabel: {
            interval: 0,
            rotate: 30,
            fontSize: 8
          },
          splitLine: {
            show: false
          }
        }],
        series: [{
          type: 'bar',
          stack: 'chart',
          z: 3,
          label: {
            normal: {
              position: 'right',
              show: false
            }
          },
          data: Object.keys(builderJson.charts).map(function(key) {
            return builderJson.charts[key]
          })
        }, {
          type: 'bar',
          stack: 'chart',
          silent: true,

          itemStyle: {
            normal: {
              color: '#eee'
            }
          },
          data: Object.keys(builderJson.charts).map(function(key) {
            return builderJson.all - builderJson.charts[key]
          })
        }, {
          type: 'bar',
          stack: 'component',
          xAxisIndex: 1,
          yAxisIndex: 1,
          z: 3,
          label: {
            normal: {
              position: 'right',
              show: false

            }
          },
          data: Object.keys(builderJson.components).map(function(key) {
            return builderJson.components[key]
          })
        }, {
          type: 'bar',
          stack: 'component',
          silent: true,
          xAxisIndex: 1,
          yAxisIndex: 1,
          itemStyle: {
            normal: {
              color: '#eee'
            }
          },
          data: Object.keys(builderJson.components).map(function(key) {
            return builderJson.all - builderJson.components[key]
          })
        }, {
          type: 'pie',
          radius: [0, '30%'],
          center: ['75%', '25%'],
          data: Object.keys(downloadJson).map(function(key) {
            return {
              name: key.replace('.js', ''),
              value: downloadJson[key]
            }
          })
        }, {
          type: 'pie',
          radius: [0, '30%'],
          center: ['75%', '75%'],
          data: Object.keys(themeJson).map(function(key) {
            return {
              name: key.replace('.js', ''),
              value: themeJson[key]
            }
          })
        }]
      }

      this.chart.setOption(option)
    }
  }
}
</script>
