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
      default: '400px'
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

      var option = {
        legend: {},
        tooltip: {
          trigger: 'axis',
          showContent: false
        },
        title:{
          text:'四类风资源区装机情况',
          subtext:'CWEA'
        },
        dataset: {
          source: [
            ['product', '2012', '2013', '2014', '2015', '2016', '2017'],
            ['I', 41.1, 30.4, 65.1, 53.3, 83.8, 98.7],
            ['II', 86.5, 92.1, 85.7, 83.1, 73.4, 55.1],
            ['III', 24.1, 67.2, 79.5, 86.4, 65.2, 82.5],
            ['IV', 55.2, 67.1, 69.2, 72.4, 53.9, 39.1]
          ]
        },
        xAxis: {
          type: 'category'
        },
        yAxis: {
          gridIndex: 0
        },
        grid: {
          left: '55%'
        },
        series: [{
            type: 'line',
            smooth: true,
            seriesLayoutBy: 'row'
          },
          {
            type: 'line',
            smooth: true,
            seriesLayoutBy: 'row'
          },
          {
            type: 'line',
            smooth: true,
            seriesLayoutBy: 'row'
          },
          {
            type: 'line',
            smooth: true,
            seriesLayoutBy: 'row'
          },
          {
            type: 'pie',
            id: 'pie',
            radius: '30%',
            center: ['25%', '50%'],
            label: {
              formatter: '{b}: {@2012} ({d}%)'
            },
            encode: {
              itemName: 'product',
              value: '2012',
              tooltip: '2012'
            }
          }
        ]
      };
      var myChart = this.chart; 
      this.chart.on('updateAxisPointer', function (event) {
        var xAxisInfo = event.axesInfo[0];
        if (xAxisInfo) {
          var dimension = xAxisInfo.value + 1;
          myChart.setOption({
            series: {
              id: 'pie',
              label: {
                formatter: '{b}: {@[' + dimension + ']} ({d}%)'
              },
              encode: {
                value: dimension,
                tooltip: dimension
              }
            }
          });
        }
      });
      this.chart.setOption(option);
    }
  }
}
</script>
