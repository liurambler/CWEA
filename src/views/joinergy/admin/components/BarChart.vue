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
      default: '300px'
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

      const row_data = [['河北', 3237.75], ['山东', 2930.0], ['宁夏', 2207.5], ['辽宁', 2012.65], ['黑龙江', 1851.0], ['山西', 1392.6], ['吉林', 1240.0], ['新疆', 1061.5], ['甘肃', 1003.5], ['云南', 747.25], ['广东', 719.3], ['江苏', 687.05], ['陕西', 453.5], ['贵州', 333.1], ['福建', 310.0], ['天津', 247.5], ['河南', 230.9], ['安徽', 198.0], ['广西', 148.5], ['湖南', 144.0], ['浙江', 102.0], ['湖北', 71.8], ['上海', 56.6], ['青海', 55.5], ['江西', 49.5], ['四川', 16.0], ['北京', 2.5]]
      const province = []
      const c_value = []
      for (let j = 0; j < row_data.length; j++) {
        province.push(row_data[j][0])
        c_value.push(row_data[j][1])
      }
      console.log('province')
      console.log(province)

      this.chart.setOption({
        tooltip: {
          trigger: 'axis',
          axisPointer: { // 坐标轴指示器，坐标轴触发有效
            type: 'shadow' // 默认为直线，可选为：'line' | 'shadow'
          }
        },
        grid: {
          top: 10,
          left: '2%',
          right: '2%',
          bottom: '3%',
          containLabel: true
        },
        xAxis: [{
          type: 'category',
          data: province,
          axisTick: {
            alignWithLabel: true
          }
        }],
        yAxis: [{
          type: 'value',
          axisTick: {
            show: false
          }
        }],
        series: [{
          name: '装机容量',
          type: 'bar',
          stack: 'vistors',
          barWidth: '60%',
          data: c_value,
          animationDuration
        }
        // , {
        //   name: 'pageB',
        //   type: 'bar',
        //   stack: 'vistors',
        //   barWidth: '60%',
        //   data: [80, 52, 200, 334, 390, 330, 220],
        //   animationDuration
        // }, {
        //   name: 'pageC',
        //   type: 'bar',
        //   stack: 'vistors',
        //   barWidth: '60%',
        //   data: [30, 52, 200, 334, 390, 330, 220],
        //   animationDuration
        // }
        ]
      })
    }
  }
}
</script>
