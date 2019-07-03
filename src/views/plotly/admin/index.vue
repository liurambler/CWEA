<template>
  <div class="dashboard-editor-container">
    <!-- <github-corner class="github-corner" />

    <panel-group @handleSetLineChartData="handleSetLineChartData" />

    <el-row style="background:#fff;padding:16px 16px 0;margin-bottom:32px;">
      <line-chart :chart-data="lineChartData" />
    </el-row>

    <el-row :gutter="32">
      <el-col :xs="24" :sm="24" :lg="8">
        <div class="chart-wrapper">
          <pie-chart />
        </div>
      </el-col>
      <el-col :xs="24" :sm="24" :lg="16">
        <div class="chart-wrapper">
          <bar-chart />
        </div>
      </el-col>
    </el-row> -->
    <div class="filter-container">
      <div class="filter-item el-input el-input--medium" style="width: 200px;">
        <!----><input type="text" autocomplete="off" placeholder="Title" class="el-input__inner">
        <!---->
        <!---->
        <!---->
      </div>
      <div class="el-select filter-item el-select--medium" style="width: 90px;">
        <!---->
        <div class="el-input el-input--medium el-input--suffix">
          <!----><input type="text" readonly="readonly" autocomplete="off" placeholder="Status" class="el-input__inner">
          <!----><span class="el-input__suffix"><span class="el-input__suffix-inner"><i
            class="el-select__caret el-input__icon el-icon-arrow-up"
          />
            <!---->
            <!---->
            <!---->
            <!----></span>
            <!----></span>
          <!---->
        </div>
        <div class="el-select-dropdown el-popper" style="display: none; min-width: 90px;">
          <div class="el-scrollbar" style="">
            <div class="el-select-dropdown__wrap el-scrollbar__wrap" style="margin-bottom: -17px; margin-right: -17px;">
              <ul class="el-scrollbar__view el-select-dropdown__list">
                <!---->
                <li class="el-select-dropdown__item"><span>1</span></li>
                <li class="el-select-dropdown__item"><span>2</span></li>
                <li class="el-select-dropdown__item"><span>3</span></li>
              </ul>
            </div>
            <div class="el-scrollbar__bar is-horizontal">
              <div class="el-scrollbar__thumb" style="transform: translateX(0%);" />
            </div>
            <div class="el-scrollbar__bar is-vertical">
              <div class="el-scrollbar__thumb" style="transform: translateY(0%);" />
            </div>
          </div>
          <!---->
        </div>
      </div>
      <div class="el-select filter-item el-select--medium" style="width: 130px;">
        <!---->
        <div class="el-input el-input--medium el-input--suffix">
          <!----><input type="text" readonly="readonly" autocomplete="off" placeholder="Owner" class="el-input__inner">
          <!----><span class="el-input__suffix"><span class="el-input__suffix-inner"><i
            class="el-select__caret el-input__icon el-icon-arrow-up"
          />
            <!---->
            <!---->
            <!---->
            <!----></span>
            <!----></span>
          <!---->
        </div>
        <div class="el-select-dropdown el-popper" style="display: none; min-width: 130px;">
          <div class="el-scrollbar" style="">
            <div class="el-select-dropdown__wrap el-scrollbar__wrap" style="margin-bottom: -17px; margin-right: -17px;">
              <ul class="el-scrollbar__view el-select-dropdown__list">
                <!---->
                <li class="el-select-dropdown__item"><span>China(CN)</span></li>
                <li class="el-select-dropdown__item"><span>USA(US)</span></li>
                <li class="el-select-dropdown__item"><span>Japan(JP)</span></li>
                <li class="el-select-dropdown__item"><span>Eurozone(EU)</span></li>
              </ul>
            </div>
            <div class="el-scrollbar__bar is-horizontal">
              <div class="el-scrollbar__thumb" style="transform: translateX(0%);" />
            </div>
            <div class="el-scrollbar__bar is-vertical">
              <div class="el-scrollbar__thumb" style="transform: translateY(0%);" />
            </div>
          </div>
          <!---->
        </div>
      </div>
      <button type="button" class="el-button filter-item el-button--primary el-button--medium">
        <!----><i class="el-icon-search" /><span>
          Search
        </span></button> <button
        type="button"
        class="el-button filter-item el-button--primary el-button--medium"
        style="margin-left: 10px;"
      >
        <!----><i class="el-icon-edit" /><span>
          Add
        </span></button> <button type="button" class="el-button filter-item el-button--primary el-button--medium">
        <!----><i class="el-icon-download" /><span>
          Output
        </span></button>
    </div>
    <div
      class="el-table el-table--fit el-table--border el-table--enable-row-hover el-table--enable-row-transition el-table--medium"
      style="width: 1000px;"
    >
      <div class="el-table__header-wrapper">
        <table cellspacing="0" cellpadding="0" border="0" class="el-table__header" style="width:100%;">
          <colgroup>
            <col name="el-table_5_column_17" width="80">
            <col name="el-table_5_column_18" width="150">
            <col name="el-table_5_column_19" width="500">
            <col name="el-table_5_column_20" width="110">
            <col name="el-table_5_column_21" width="80">
            <col name="el-table_5_column_22" width="80">

            <col name="gutter" width="0">
          </colgroup>
          <thead class="has-gutter">
            <tr class="">
              <th
                colspan="1"
                rowspan="1"
                class="el-table_5_column_17  is-center   is-leaf is-sortable"
                style="cursor: col-resize;"
              >
                <div class="cell">No<span class="caret-wrapper"><i class="sort-caret ascending" /><i
                  class="sort-caret descending"
                /></span></div>
              </th>
              <th colspan="1" rowspan="1" class="el-table_5_column_18  is-center   is-leaf">
                <div class="cell">Timestamp</div>
              </th>
              <th colspan="1" rowspan="1" class="el-table_5_column_19     is-leaf">
                <div class="cell">Title</div>
              </th>
              <th colspan="1" rowspan="1" class="el-table_5_column_20  is-center   is-leaf">
                <div class="cell">Owner</div>
              </th>
              <th colspan="1" rowspan="1" class="el-table_5_column_23   status-col  is-leaf">
                <div class="cell">Status</div>
              </th>
              <th colspan="1" rowspan="1" class="el-table_5_column_24  is-center small-padding fixed-width  is-leaf">
                <div class="cell">Action</div>
              </th>
              <th class="gutter" style="width: 0px; display: none;" />
            </tr>
          </thead>
        </table>
      </div>
      <div class="el-table__body-wrapper is-scrolling-none">
        <table cellspacing="0" cellpadding="0" border="0" class="el-table__body" style="width:100%;">
          <colgroup>
            <col name="el-table_5_column_17" width="80">
            <col name="el-table_5_column_18" width="150">
            <col name="el-table_5_column_19" width="500">
            <col name="el-table_5_column_20" width="110">
            <col name="el-table_5_column_21" width="80">
            <col name="el-table_5_column_22" width="80">
          </colgroup>
          <tbody>
            <tr class="el-table__row">
              <td rowspan="1" colspan="1" class="el-table_5_column_17 is-center ">
                <div class="cell"><span>1</span></div>
              </td>
              <td rowspan="1" colspan="1" class="el-table_5_column_18 is-center ">
                <div class="cell"><span>2018-10-16 11:38</span></div>
              </td>
              <td rowspan="1" colspan="1" class="el-table_5_column_19  ">
                <div class="cell"><span class="link-type">Test_demo_01</span></div>
              </td>
              <td rowspan="1" colspan="1" class="el-table_5_column_20 is-center ">
                <div class="cell"><span>Teddy</span></div>
              </td>
              <td rowspan="1" colspan="1" class="el-table_5_column_21  status-col">
                <div class="cell"><span class="el-tag el-tag--danger el-tag--medium">
                  deleted
                </span></div>
              </td>
              <td rowspan="1" colspan="1" class="el-table_5_column_22 is-center small-padding">
                <div class="cell"><button type="button" class="el-button el-button--primary el-button--mini">
                  <!---->
                  <!----><span>
                    Edit
                  </span></button>
                  <!---->
                </div>
              </td>
            </tr>
            <!---->
          </tbody>
        </table>
        <!---->
        <!---->
      </div>
      <!---->
      <!---->
      <!---->
      <!---->
      <div class="el-table__column-resize-proxy" style="display: none;" />
      <div class="el-loading-mask" style="display: none;">
        <div class="el-loading-spinner"><svg viewBox="25 25 50 50" class="circular">
          <circle cx="50" cy="50" r="20" fill="none" class="path" />
        </svg>
          <!---->
        </div>
      </div>
    </div>

    <el-row :gutter="32" style="padding-top:20px">
      <el-col :xs="24" :sm="24" :lg="16">
        <div class="chart-wrapper">
          <div id="plot" style="width:100%;height:400px;margin:auto;" />
        </div>
      </el-col>
      <el-col :xs="24" :sm="24" :lg="8">
        <div class="chart-wrapper">
          <div
            class="el-table el-table--fit el-table--enable-row-hover el-table--enable-row-transition el-table--medium"
            style="width: 100%; padding-top: 15px;height:400px;"
          >
            <div class="el-table__header-wrapper">
              <h3 style="text-align: center">Data Validation&nbsp;&nbsp;<span class="el-tag el-tag--success el-tag--medium">
                Pass
              </span></h3>
              <table cellspacing="0" cellpadding="0" border="0" class="el-table__header" style="width: 100%;height:400px;">

                <thead class="has-gutter">
                  <tr class="">
                    <th colspan="1" rowspan="1" class="     is-leaf">
                      <div class="cell">Data Qualification</div>
                    </th>
                    <th colspan="1" rowspan="1" class=" is-center   is-leaf">
                      <div class="cell">Status</div>
                    </th>
                  </tr>
                </thead>
              </table>
            </div>
            <div class="el-table__body-wrapper is-scrolling-none">

              <table cellspacing="0" cellpadding="0" border="0" class="el-table__body" style="width: 100%;">
                <colgroup />
                <tbody>
                  <tr class="el-table__row">
                    <td rowspan="1" colspan="1" class="  ">
                      <div class="cell">
                        Tabel header
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="is-center ">
                      <div class="cell"><span class="el-tag el-tag--success el-tag--medium">
                        Pass
                      </span></div>
                    </td>
                  </tr>

                  <tr class="el-table__row">
                    <td rowspan="1" colspan="1" class="  ">
                      <div class="cell">
                        Timestamp Format
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="el-table_1_column_3 is-center ">
                      <div class="cell"><span class="el-tag el-tag--success el-tag--medium">
                        Pass
                      </span></div>
                    </td>
                  </tr>
                  <tr class="el-table__row">
                    <td rowspan="1" colspan="1" class="  ">
                      <div class="cell">
                        Single Variable for Loads
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="el-table_1_column_3 is-center ">
                      <div class="cell"><span class="el-tag el-tag--success el-tag--medium">
                        Pass
                      </span></div>
                    </td>
                  </tr>
                  <tr class="el-table__row">
                    <td rowspan="1" colspan="1" class="  ">
                      <div class="cell">
                        Without duplicated Timestep
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="el-table_1_column_3 is-center ">
                      <div class="cell"><span class="el-tag el-tag--success el-tag--medium">
                        Pass
                      </span></div>
                    </td>
                  </tr>

                  <!---->
                </tbody>
              </table>
              <!---->
              <!---->
            </div>
            <!---->
            <!---->
            <!---->
            <!---->
            <div class="el-table__column-resize-proxy" style="display: none;" />
          </div>
        </div>
      </el-col>
    </el-row>

    <el-row :gutter="32" style="">
      <el-col :xs="24" :sm="24" :lg="6">
        <div class="chart-wrapper">
          <div
            class="el-table el-table--fit el-table--enable-row-hover el-table--enable-row-transition el-table--medium"
            style="width: 100%; padding-top: 15px;height:400px;"
          >
            <div class="el-table__header-wrapper">
              <h3 style="text-align: center">Data Properties</h3>
              <table cellspacing="0" cellpadding="0" border="0" class="el-table__header" style="width: 100%;height:400px;">

                <thead class="has-gutter">
                  <tr class="">
                    <th colspan="1" rowspan="1" class="     is-leaf">
                      <div class="cell">Data Properties</div>
                    </th>
                    <th colspan="1" rowspan="1" class=" is-center   is-leaf">
                      <div class="cell">Value</div>
                    </th>
                  </tr>
                </thead>
              </table>
            </div>
            <div class="el-table__body-wrapper is-scrolling-none">
              <table cellspacing="0" cellpadding="0" border="0" class="el-table__body" style="width: 100%;">
                <colgroup />
                <tbody>
                  <tr class="el-table__row">
                    <td rowspan="1" colspan="1" class="  ">
                      <div class="cell">
                        Start Timestamp
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="is-center ">
                      <div class="cell"><span class="el-tag el-tag--success el-tag--medium">
                        2018-04-01 00:05:00
                      </span></div>
                    </td>
                  </tr>
                  <tr class="el-table__row">
                    <td rowspan="1" colspan="1" class="  ">
                      <div class="cell">
                        End Timestamp
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="el-table_1_column_3 is-center ">
                      <div class="cell"><span class="el-tag el-tag--success el-tag--medium">
                        2018-06-30 23:55:00
                      </span></div>
                    </td>
                  </tr>
                  <tr class="el-table__row">
                    <td rowspan="1" colspan="1" class="  ">
                      <div class="cell">
                        Time Range
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="el-table_1_column_3 is-center ">
                      <div class="cell"><span class="el-tag el-tag--success el-tag--medium">
                        90 days 23:50:00
                      </span></div>
                    </td>
                  </tr>
                  <tr class="el-table__row">
                    <td rowspan="1" colspan="1" class="  ">
                      <div class="cell">
                        Time Step
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="el-table_1_column_3 is-center ">
                      <div class="cell"><span class="el-tag el-tag--success el-tag--medium">
                        00:05:00
                      </span></div>
                    </td>
                  </tr>
                  <tr class="el-table__row">
                    <td rowspan="1" colspan="1" class="  ">
                      <div class="cell">
                        Count
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="el-table_1_column_3 is-center ">
                      <div class="cell"><span class="el-tag el-tag--success el-tag--medium">
                        26205
                      </span></div>
                    </td>
                  </tr>
                  <!---->
                </tbody>
              </table>
              <!---->
              <!---->
            </div>
            <!---->
            <!---->
            <!---->
            <!---->
            <div class="el-table__column-resize-proxy" style="display: none;" />
          </div>
        </div>
      </el-col>
      <el-col :xs="24" :sm="24" :lg="6">
        <div class="chart-wrapper">
          <div
            class="el-table el-table--fit el-table--enable-row-hover el-table--enable-row-transition el-table--medium"
            style="width: 100%; padding-top: 15px;height:400px;"
          >
            <div class="el-table__header-wrapper">
              <h3 style="text-align: center">Statistic Features</h3>
              <table cellspacing="0" cellpadding="0" border="0" class="el-table__header" style="width: 100%;height:400px;">

                <thead class="has-gutter">
                  <tr class="">
                    <th colspan="1" rowspan="1" class="     is-leaf">
                      <div class="cell">Features</div>
                    </th>
                    <th colspan="1" rowspan="1" class=" is-center   is-leaf">
                      <div class="cell">Value</div>
                    </th>
                  </tr>
                </thead>
              </table>
            </div>
            <div class="el-table__body-wrapper is-scrolling-none">
              <table cellspacing="0" cellpadding="0" border="0" class="el-table__body" style="width: 100%;">
                <colgroup />
                <tbody>
                  <tr class="el-table__row">
                    <td rowspan="1" colspan="1" class="  ">
                      <div class="cell">
                        Max
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="is-center ">
                      <div class="cell">
                        26.3154
                      </div>
                    </td>
                  </tr>
                  <tr class="el-table__row">
                    <td rowspan="1" colspan="1" class="  ">
                      <div class="cell">
                        Min
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="el-table_1_column_3 is-center ">
                      <div class="cell">
                        1.7603
                      </div>
                    </td>
                  </tr>
                  <tr class="el-table__row">
                    <td rowspan="1" colspan="1" class="  ">
                      <div class="cell">
                        Mean
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="el-table_1_column_3 is-center ">
                      <div class="cell">
                        18.0266
                      </div>
                    </td>
                  </tr>
                  <tr class="el-table__row">
                    <td rowspan="1" colspan="1" class="  ">
                      <div class="cell">
                        variance
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="el-table_1_column_3 is-center ">
                      <div class="cell">15.9579</div>
                    </td>
                  </tr>
                  <tr class="el-table__row">
                    <td rowspan="1" colspan="1" class="  ">
                      <div class="cell">
                        kurtosis
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="el-table_1_column_3 is-center ">
                      <div class="cell">
                        3.7243
                      </div>
                    </td>
                  </tr>
                  <tr class="el-table__row">
                    <td rowspan="1" colspan="1" class="  ">
                      <div class="cell">
                        skewness
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="el-table_1_column_3 is-center ">
                      <div class="cell">
                        -1.6717
                      </div>
                    </td>
                  </tr>
                  <!---->
                </tbody>
              </table>
              <!---->
              <!---->
            </div>
            <!---->
            <!---->
            <!---->
            <!---->
            <div class="el-table__column-resize-proxy" style="display: none;" />
          </div>
        </div>
      </el-col>
      <el-col :xs="24" :sm="24" :lg="12">
        <div class="chart-wrapper">
          <div id="myDiv1" style="width:90%;height:400px;margin:auto;" />
        </div>
      </el-col>
    </el-row>
    <el-row :gutter="32" style="">
      <el-col :xs="24" :sm="24" :lg="12">
        <div class="chart-wrapper">
          <div id="myDiv2" style="width:90%;height:400px;margin:auto;" />
        </div>
      </el-col>
      <el-col :xs="24" :sm="24" :lg="12">
        <div class="chart-wrapper">
          <div id="myDiv3" style="width:90%;height:400px;margin:auto;" />
        </div>
      </el-col>
    </el-row>

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
import axios from 'axios'
import $ from 'jquery'

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
