<template>
  <div :class="className" :style="{height:height,width:width}" />
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
      let data_f1=[{
                name: '北京',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '天津',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '上海',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '重庆',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '河北',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '河南',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '云南',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '辽宁',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '黑龙江',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '湖南',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '安徽',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '山东',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '新疆',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '江苏',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '浙江',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '江西',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '湖北',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '广西',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '甘肃',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '山西',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '内蒙古',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '陕西',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '吉林',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '福建',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '贵州',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '广东',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '青海',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '西藏',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '四川',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '宁夏',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '海南',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '台湾',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '香港',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '澳门',
                value: Math.round(Math.random() * 100)
              }
            ],
      data_f2 = [{
                name: '北京',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '天津',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '上海',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '广东',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '台湾',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '香港',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '澳门',
                value: Math.round(Math.random() * 100)
              }
            ],
      data_f3 = [{
                name: '北京',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '天津',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '上海',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '重庆',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '河北',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '安徽',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '新疆',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '浙江',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '江西',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '山西',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '内蒙古',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '吉林',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '福建',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '广东',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '西藏',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '四川',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '宁夏',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '香港',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '澳门',
                value: Math.round(Math.random() * 100)
              }
            ],
      data_f4 = [{
                name: '北京',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '天津',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '上海',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '重庆',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '河北',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '河南',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '云南',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '辽宁',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '黑龙江',
                value: Math.round(Math.random() * 100)
              },
            ],
      data_f5 = [{
                name: '北京',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '天津',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '上海',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '重庆',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '河北',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '河南',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '云南',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '辽宁',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '黑龙江',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '湖南',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '安徽',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '山东',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '新疆',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '江苏',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '四川',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '宁夏',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '海南',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '台湾',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '香港',
                value: Math.round(Math.random() * 100)
              },
              {
                name: '澳门',
                value: Math.round(Math.random() * 100)
              }
            ];
      this.chart = echarts.init(this.$el, 'macarons')
      this.chart.setOption({
        title: {
          text: '项目进展全国分布',
          subtext: '虚构数据',
          left: 'center'
        },
        tooltip: {
          trigger: 'item',
          formatter: '{b} : {c}'
        },
        legend: {
          orient: 'vertical',
          left: 'left',
          data: ['已签订《风电项目开发协议》', '完成风资源评估与可研', '项目核准', '开工建设', '并网运行']
        },

        visualMap: {
          min: 0,
          max: 400,
          top: 'bottom',
          text: ['高', '低'], // 文本，默认为数值文本
          calculable: true
        },
        toolbox: {
          show: true,
          orient: 'vertical',
          left: 'right',
          top: 'center',
          feature: {
            mark: {
              show: true
            },
            dataView: {
              show: true,
              readOnly: false
            },
            restore: {
              show: true
            },
            saveAsImage: {
              show: true
            }
          }
        },
        series: [
          {
            name: '已签订《风电项目开发协议》',
            type: 'map',
            mapType: 'china',
            roam: false,
            left: '10%',
            label: {
              normal: {
                show: false
              },
              emphasis: {
                show: true
              }
            },
            showLegendSymbol: false,
            data: data_f1,
            itemStyle: {
              normal: {
                label: {
                  show: false
                },
                borderColor: '#fff',
              },
              emphasis: {
                label: {
                  show: true
                },
                borderColor: '#ddd',
              }
            },
          },
          {
            name: '完成风资源评估与可研',
            type: 'map',
            mapType: 'china',
            
            label: {
              normal: {
                show: false
              },
              emphasis: {
                show: true
              }
            },
            showLegendSymbol: false,
            data: data_f2,
            itemStyle: {
              normal: {
                label: {
                  show: false
                },
                borderColor: '#fff',
              },
              emphasis: {
                label: {
                  show: true
                },
                borderColor: '#ddd',
              }
            },
          },
          {
            name: '项目核准',
            type: 'map',
            mapType: 'china',
            
            label: {
              normal: {
                show: false
              },
              emphasis: {
                show: true
              }
            },
            showLegendSymbol: false,
            data: data_f3,
            itemStyle: {
              normal: {
                label: {
                  show: false
                },
                borderColor: '#fff',
              },
              emphasis: {
                label: {
                  show: true
                },
                borderColor: '#ddd',
              }
            },
          },
          {
            name: '开工建设',
            type: 'map',
            mapType: 'china',
            
            roam: false,
            label: {
              normal: {
                show: false
              },
              emphasis: {
                show: true
              }
            },
            showLegendSymbol: false,
            data: data_f4,
            itemStyle: {
              normal: {
                label: {
                  show: false
                },
                borderColor: '#fff',
              },
              emphasis: {
                label: {
                  show: true
                },
                borderColor: '#ddd',
              }
            },
          },
          {
            name: '并网运行',
            type: 'map',
            mapType: 'china',
            
            roam: false,
            label: {
              normal: {
                show: false
              },
              emphasis: {
                show: true
              }
            },
            showLegendSymbol: false,
            data: data_f5,
            itemStyle: {
              normal: {
                label: {
                  show: false
                },
                borderColor: '#fff',
              },
              emphasis: {
                label: {
                  show: true
                },
                borderColor: '#ddd',
              }
            },
          },
          {
            name: '资源区',
            type: 'pie',
            roseType: 'radius',
            radius: [15, 60],
            center: ['75%', '50%'],
            data: [
              { value: data_f1.reduce((total, item)=>total +item.value,0),name: '已签订《风电项目开发协议》' },
              { value: data_f2.reduce((total, item)=>total +item.value,0), name: '完成风资源评估与可研' },
              { value: data_f3.reduce((total, item)=>total +item.value,0), name: '项目核准' },
              { value: data_f4.reduce((total, item)=>total +item.value,0), name: '开工建设' },
              { value: data_f5.reduce((total, item)=>total +item.value,0), name: '并网运营' }
            ],
            tooltip : {
              trigger: 'item',
              formatter: "{b} : {c} ({d}%)"
            },
            animationEasing: 'cubicInOut',
            animationDuration: 2600
          }
        ]
      })
    }
  }
}
</script>
