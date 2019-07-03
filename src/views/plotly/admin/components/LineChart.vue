<template>
  <div :class="className" :style="{height:height,width:width}" />
</template>

<script>
import echarts from 'echarts'
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
      default: '350px'
    },
    autoResize: {
      type: Boolean,
      default: true
    },
    chartData: {
      type: Object,
      required: true
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
            data: ['2011-01-01', '2012-01-01', '2013-01-01']
          },
          title: {
            text: '2011全国风电新增装机情况）',
            subtext: 'CWEA'
          },
          tooltip: {
            trigger: 'item'
          },
          // legend: {
          //     x:'right',
          //     selectedMode:false,
          //     data:['北京','上海','广东']
          // },
          dataRange: {
            orient: 'horizontal',
            min: 0,
            max: 55000,
            text: ['高', '低'], // 文本，默认为数值文本
            splitNumber: 0
          },
          toolbox: {
            show: true,
            orient: 'vertical',
            x: 'right',
            y: 'center',
            feature: {
              mark: { show: true },
              dataView: { show: true, readOnly: false }
            }
          },
          series: [
            {
              name: '2011',
              type: 'map',
              mapType: 'china'
              // mapLocation: {
              //     x: 'left'
              // },
              // selectedMode : 'multiple',
              // itemStyle:{
              //     normal:{label:{show:true}},
              //     emphasis:{label:{show:true}}
              // },
            }
          ]
        },
        options: [
          {
            title: {
              text: '2011年统计值'
            },
            series: [
              {
                data: [
                  { name: '西藏', value: 605.83 },
                  { name: '青海', value: 1670.44 },
                  { name: '宁夏', value: 2102.21 }
                ]
              }
            ]
          },
          {
            title: {
              text: '2012年统计值'
            },
            series: [
              {
                data: [
                  { name: '西藏', value: 605.83 },
                  { name: '青海', value: 1670.44 },
                  { name: '宁夏', value: 2102.21 }
                ]
              }
            ]
          },
          {
            title: {
              text: '2013年统计值'
            },
            series: [
              {
                data: [
                  { name: '西藏', value: 605.83 },
                  { name: '青海', value: 1670.44 },
                  { name: '宁夏', value: 2102.21 }
                ]
              }
            ]
          }
        ]
      })
    }
  }
}
</script>
