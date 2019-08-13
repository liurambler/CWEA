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
        <!----><input type="text" autocomplete="off" placeholder="名称" class="el-input__inner">
        <!---->
        <!---->
        <!---->
      </div>
      <div class="el-select filter-item el-select--medium" style="width: 90px;">
        <!---->
        <div class="el-input el-input--medium el-input--suffix">
          <!----><input type="text" readonly="readonly" autocomplete="off" placeholder="状态" class="el-input__inner">
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
          <!----><input type="text" readonly="readonly" autocomplete="off" placeholder="创建人" class="el-input__inner">
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
          搜索
        </span></button> <button
        type="button"
        class="el-button filter-item el-button--primary el-button--medium"
        style="margin-left: 10px;"
      >
        <!----><i class="el-icon-edit" /><span>
          添加
        </span></button> <button type="button" class="el-button filter-item el-button--primary el-button--medium">
        <!----><i class="el-icon-download" /><span>
          导出
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
                <div class="cell">编号<span class="caret-wrapper"><i class="sort-caret ascending" /><i
                  class="sort-caret descending"
                /></span></div>
              </th>
              <th colspan="1" rowspan="1" class="el-table_5_column_18  is-center   is-leaf">
                <div class="cell">创建时间</div>
              </th>
              <th colspan="1" rowspan="1" class="el-table_5_column_19     is-leaf">
                <div class="cell">名称</div>
              </th>
              <th colspan="1" rowspan="1" class="el-table_5_column_20  is-center   is-leaf">
                <div class="cell">创建人</div>
              </th>
              <th colspan="1" rowspan="1" class="el-table_5_column_23   status-col  is-leaf">
                <div class="cell">状态</div>
              </th>
              <th colspan="1" rowspan="1" class="el-table_5_column_24  is-center small-padding fixed-width  is-leaf">
                <div class="cell">操作</div>
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
                <div class="cell"><span class="link-type">测试_01</span></div>
              </td>
              <td rowspan="1" colspan="1" class="el-table_5_column_20 is-center ">
                <div class="cell"><span>张三</span></div>
              </td>
              <td rowspan="1" colspan="1" class="el-table_5_column_21  status-col">
                <div class="cell"><span class="el-tag el-tag--danger el-tag--medium">
                  待设置
                </span></div>
              </td>
              <td rowspan="1" colspan="1" class="el-table_5_column_22 is-center small-padding">
                <div class="cell"><button type="button" class="el-button el-button--primary el-button--mini">
                  <!---->
                  <!----><span>
                    编辑
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
              <h3 style="text-align: center">数据完整性验证&nbsp;&nbsp;<span class="el-tag el-tag--success el-tag--medium">
                正常
              </span></h3>
              <table cellspacing="0" cellpadding="0" border="0" class="el-table__header" style="width: 100%;height:400px;">

                <thead class="has-gutter">
                  <tr class="">
                    <th colspan="1" rowspan="1" class="     is-leaf">
                      <div class="cell">数据质量</div>
                    </th>
                    <th colspan="1" rowspan="1" class=" is-center   is-leaf">
                      <div class="cell">检测结果</div>
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
                        文件头
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="is-center ">
                      <div class="cell"><span class="el-tag el-tag--success el-tag--medium">
                        正常
                      </span></div>
                    </td>
                  </tr>

                  <tr class="el-table__row">
                    <td rowspan="1" colspan="1" class="  ">
                      <div class="cell">
                        时间戳格式
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="el-table_1_column_3 is-center ">
                      <div class="cell"><span class="el-tag el-tag--success el-tag--medium">
                        正常
                      </span></div>
                    </td>
                  </tr>
                  <tr class="el-table__row">
                    <td rowspan="1" colspan="1" class="  ">
                      <div class="cell">
                        变量对应关系
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="el-table_1_column_3 is-center ">
                      <div class="cell"><span class="el-tag el-tag--success el-tag--medium">
                        正常
                      </span></div>
                    </td>
                  </tr>
                  <tr class="el-table__row">
                    <td rowspan="1" colspan="1" class="  ">
                      <div class="cell">
                        时间戳唯一性
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="el-table_1_column_3 is-center ">
                      <div class="cell"><span class="el-tag el-tag--success el-tag--medium">
                        正常
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
              <h3 style="text-align: center">基础特性</h3>
              <table cellspacing="0" cellpadding="0" border="0" class="el-table__header" style="width: 100%;height:400px;">

                <thead class="has-gutter">
                  <tr class="">
                    <th colspan="1" rowspan="1" class="     is-leaf">
                      <div class="cell">特性</div>
                    </th>
                    <th colspan="1" rowspan="1" class=" is-center   is-leaf">
                      <div class="cell">值</div>
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
                        起始时间戳
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
                        终止时间戳
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
                        时间跨度
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
                        采样频率
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
                       数据点数
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
              <h3 style="text-align: center">统计特征</h3>
              <table cellspacing="0" cellpadding="0" border="0" class="el-table__header" style="width: 100%;height:400px;">

                <thead class="has-gutter">
                  <tr class="">
                    <th colspan="1" rowspan="1" class="     is-leaf">
                      <div class="cell">指标名称</div>
                    </th>
                    <th colspan="1" rowspan="1" class=" is-center   is-leaf">
                      <div class="cell">值</div>
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
                        最大值
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
                        最小值
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
                        均值
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
                        方差
                      </div>
                    </td>
                    <td rowspan="1" colspan="1" class="el-table_1_column_3 is-center ">
                      <div class="cell">15.9579</div>
                    </td>
                  </tr>
                  <tr class="el-table__row">
                    <td rowspan="1" colspan="1" class="  ">
                      <div class="cell">
                        峰态系数
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
                       偏态系数
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
          <div id="myDiv2" style="width:90%;height:400px;margin:auto;" />
        </div>
      </el-col>
    </el-row>
    <el-row :gutter="32" style="">
      <el-col :xs="24" :sm="24" :lg="12">
        <div class="chart-wrapper">
          <div id="myDiv1" style="width:90%;height:400px;margin:auto;" />
        </div>
      </el-col>
      <el-col :xs="24" :sm="24" :lg="12">
        <div class="chart-wrapper">
          <div id="myDiv3" style="width:90%;height:400px;margin:auto;" />
        </div>
      </el-col>
    </el-row>
    <el-row :gutter="32" style="">
      <el-col :xs="24" :sm="24" :lg="12">
        <div class="chart-wrapper">
          <div id="myDiv4" style="width:90%;height:400px;margin:auto;" />
        </div>
      </el-col>
      <el-col :xs="24" :sm="24" :lg="12">
        <div class="chart-wrapper">
          <div id="myDiv5" style="width:90%;height:400px;margin:auto;" />
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
    this.initAbnormalChart()
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
        title: '原始数据'
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
            name: '趋势性',
            type: 'scatter'
          }

          const trace2 = {
            x: json.x,
            y: json.residual,
            xaxis: 'x2',
            yaxis: 'y2',
            name: '残差',
            type: 'scatter'
          }

          const trace3 = {
            x: json.x,
            y: json.seasonal,
            xaxis: 'x3',
            yaxis: 'y3',
            name: '周期性',
            type: 'scatter'
          }

          const trace4 = {
            x: json.X_histo,
            name: '直方图',
            type: 'histogram'
          }

          const trace5 = {
            y: json.kde_gaussan,
            xaxis: 'x2',
            yaxis: 'y2',
            name: '核密度估计（高斯核）',
            type: 'scatter'
          }

          const trace6 = {
            y: json.kde_tophat,
            xaxis: 'x2',
            yaxis: 'y2',
            name: '核密度估计（帽顶核）',
            type: 'scatter'
          }
          const data = [trace1, trace2, trace3]

          var layout = {
            title: '周期稳定性分析',
            grid: {
              rows: 3,
              columns: 1,
              pattern: 'independent'
            }
          }

          plotly.newPlot('myDiv1', data, layout, { showSendToCloud: false }, { responsive: true })

          const data2 = [trace4, trace5, trace6]
          const layout2 = {
            title: '采样（真实）密度',

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
            name: '一阶',
            type: 'scatter'
          }
          const trace2 = {
            x: json.log_index,
            y: json.log_diff2,
            name: '二阶',
            type: 'scatter'
          }
          const layout = {
            title: '差分稳定性'
          }
          plotly.newPlot('myDiv3', [trace1, trace2], layout)
        }
      })
    },
    initAbnormalChart(){
        // 载入json数据
      $.ajax({
        url: 'http://localhost:9527/step_5_ta_fo_data.json', // json文件位置
        type: 'GET', // 请求方式为get
        async: false,
        dataType: 'json', // 返回数据格式为json
        success: function(json) { // 请求成功完成后要执行的方法
          console.log('json data acquired')

          // tableData = json.feature;
          const trace1 = {

            y: json.KL,
            name: 'KL',
            type: 'scatter'
          }

          const trace2 = {
            y: json.hurst_series,
            xaxis: 'x2',
            yaxis: 'y2',
            name: 'hurst_series',
            type: 'scatter'
          }

          const trace3 = {
            y: json.sst_value,
            xaxis: 'x3',
            yaxis: 'y3',
            name: 'sst_value',
            type: 'scatter'
          }

          const data = [trace1, trace2, trace3]

          var layout = {
            title: '特征工程分析',
            grid: {
              rows: 3,
              columns: 1,
              pattern: 'independent'
            }
          }

          plotly.newPlot('myDiv4', data, layout, { showSendToCloud: false }, { responsive: true })
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
