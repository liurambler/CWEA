<template>
  <div class="dashboard-editor-container">

    <el-row :gutter="32">
      <el-col :xs="24" :sm="24" :lg="16">
        <div class="chart-wrapper">
          <line-chart :chart-data="lineChartData" />
        </div>
      </el-col>
      <el-col :xs="24" :sm="24" :lg="8">
        <div class="chart-wrapper">
          <pie-chart />
        </div>
      </el-col>
    </el-row>


    <img src="@/suzhou_temp.png">
    <iframe src="https://www.jiaonengwang.com/EVdaily.html"   frameborder="0" scrolling="auto" width="100%" height="1000px;" onload="document.all['myframe'].style.width=myframe.document.body.scrollWidth" ></iframe>
  </div>

</template>

<script>
import GithubCorner from '@/components/GithubCorner'
import PanelGroup from './components/PanelGroup'
import LineChart from './components/LineChart'
import RaddarChart from './components/RaddarChart'
import PieChart from './components/PieChart'
import BarChart from './components/BarChart'

import TransactionTable from './components/TransactionTable'
import TodoList from './components/TodoList'
import BoxCard from './components/BoxCard'

import plotly from 'plotly.js-dist'
import $ from 'jquery'
import AreaDev from './components/AreaDev'

const lineChartData = {
  newVisitis: {
    expectedData: [100, 120, 161, 134, 105, 160, 165],
    actualData: [120, 82, 91, 154, 162, 140, 145]
  },
  messages: {
    expectedData: [200, 192, 120, 144, 160, 130, 140],
    actualData: [180, 160, 151, 106, 145, 150, 130]
  },
  purchases: {
    expectedData: [80, 100, 121, 104, 105, 90, 100],
    actualData: [120, 90, 100, 138, 142, 130, 130]
  },
  shoppings: {
    expectedData: [130, 140, 141, 142, 145, 150, 160],
    actualData: [120, 82, 91, 154, 162, 140, 130]
  }
}

export default {
  name: 'DashboardAdmin',
  components: {
    GithubCorner,
    PanelGroup,
    LineChart,
    RaddarChart,
    PieChart,
    BarChart,
    AreaDev,
    TransactionTable,
    TodoList,
    BoxCard
  },
  data() {
    return {
      lineChartData: lineChartData.newVisitis
    }
  },
  mounted() {
    this.initPlotlyLineChart()
    this.initPlotlySeaonalChart()
  },
  methods: {

    handleSetLineChartData(type) {
      this.lineChartData = lineChartData[type]
    },
    initPlotlyLineChart() {
      let plotDataX = []
      let plotDataY = []
      $.ajax({
        url: 'http://localhost:9527/step_2_data.json', // json文件位置
        type: 'GET', // 请求方式为get
        async: false,
        dataType: 'json', // 返回数据格式为json
        success: function(json) { // 请求成功完成后要执行的方法
          console.log('json data acquired')
          console.log(json)
          plotDataX = json.data.x
          plotDataY = json.data.y
        }
      })

      const PLOT = document.getElementById('plot')

      const trace = {
        x: plotDataX,
        y: plotDataY,
        type: 'scatter'

      }
      var layout = {
        title: 'Raw Data Plot'
      }

      plotly.newPlot(PLOT, [trace], layout)
    },
    initPlotlySeaonalChart() {
      // 载入json数据
      $.ajax({
        url: 'http://localhost:9527/step_3_data.json', // json文件位置
        type: 'GET', // 请求方式为get
        async: false,
        dataType: 'json', // 返回数据格式为json
        success: function(json) { // 请求成功完成后要执行的方法
          console.log('json data acquired')

          // tableData = json.feature;
          const trace1 = {
            x: json.x,
            y: json.trend,
            name: 'Trend',
            type: 'scatter'
          }

          const trace2 = {
            x: json.x,
            y: json.residual,
            xaxis: 'x2',
            yaxis: 'y2',
            name: 'Residual',
            type: 'scatter'
          }

          const trace3 = {
            x: json.x,
            y: json.seasonal,
            xaxis: 'x3',
            yaxis: 'y3',
            name: 'Seasonal',
            type: 'scatter'
          }

          const trace4 = {
            x: json.X_histo,
            name: 'X_histo',
            type: 'histogram'
          }

          const trace5 = {
            y: json.kde_gaussan,
            xaxis: 'x2',
            yaxis: 'y2',
            name: 'kde_gaussan',
            type: 'scatter'
          }

          const trace6 = {
            y: json.kde_tophat,
            xaxis: 'x2',
            yaxis: 'y2',
            name: 'kde_tophat',
            type: 'scatter'
          }
          const data = [trace1, trace2, trace3]

          var layout = {
            title: 'Seasonal',
            grid: {
              rows: 3,
              columns: 1,
              pattern: 'independent'
            }
          }

          plotly.newPlot('myDiv1', data, layout, { showSendToCloud: false }, { responsive: true })

          const data2 = [trace4, trace5, trace6]
          const layout2 = {
            title: 'Histogramm',

            xaxis2: {
              overlaying: 'x',
              showticklabels: false
            },
            yaxis2: {
              rangemode: 'nonnegative',
              showgrid: false,
              overlaying: 'y',
              side: 'right'
            }
          }

          plotly.newPlot('myDiv2', data2, layout2)
        }

      })
      $.ajax({
        url: 'http://localhost:9527/step_4_df_log_1_2.json', // json文件位置
        type: 'GET', // 请求方式为get
        async: false,
        dataType: 'json', // 返回数据格式为json
        success: function(json) { // 请求成功完成后要执行的方法
          console.log('json data acquired')
          const trace1 = {
            x: json.log_index,
            y: json.log_diff1,
            name: 'diff1',
            type: 'scatter'
          }
          const trace2 = {
            x: json.log_index,
            y: json.log_diff2,
            name: 'diff2',
            type: 'scatter'
          }
          const layout = {
            title: '1st & 2nd Differential'
          }
          plotly.newPlot('myDiv3', [trace1, trace2], layout)
        }
      })
    }
  }
}

</script>

<style lang="scss" scoped>
  .dashboard-editor-container {
    padding: 32px;
    background-color: rgb(240, 242, 245);
    position: relative;

    .github-corner {
      position: absolute;
      top: 0px;
      border: 0;
      right: 0;
    }

    .chart-wrapper {
      background: #fff;
      padding: 16px 16px 0;
      margin-bottom: 32px;
    }
  }

  @media (max-width:1024px) {
    .chart-wrapper {
      padding: 8px;
    }
  }

</style>
