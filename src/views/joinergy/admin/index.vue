<template>
  <div class="dashboard-editor-container">
    <h1>数字化风能产业地图</h1>
    <el-row :gutter="32">
      <el-col :xs="24" :sm="24" :lg="8">
        <div class="chart-wrapper">
          <line-chart :chart-data="lineChartData" />
        </div>
      </el-col>
      <el-col :xs="24" :sm="24" :lg="16">
        <div class="chart-wrapper">
          <area-dev/>
        </div>
      </el-col>
    </el-row>
        <el-row :gutter="32">
      <el-col :xs="24" :sm="24" :lg="24">
        <div class="chart-wrapper">
          <line-chart-new :chart-data="lineChartData" />
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import GithubCorner from '@/components/GithubCorner'
import PanelGroup from './components/PanelGroup'
import LineChart from './components/LineChart'
import LineChartNew from './components/LineChartNew'
import RaddarChart from './components/RaddarChart'
import PieChart from './components/PieChart'
import BarChart from './components/BarChart'

import TransactionTable from './components/TransactionTable'
import TodoList from './components/TodoList'
import BoxCard from './components/BoxCard'

import plotly from 'plotly.js-dist'
import $ from 'jquery'
import AreaDev from './components/AreaDev'
// import d3 from 'd3'
// import './components/viz.v1.1.0.min.js'

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
    LineChartNew,
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
      
var data=
[['制造企业1', '开发商16', 247.5], ['制造企业1', '开发商2', 268.0], ['制造企业1', '开发商3', 483.5], ['制造企业1', '开发商4', 493.5], ['制造企业1', '开发商6', 398.5], ['制造企业1', '开发商7', 148.5], ['制造企业1', '开发商8', 583.5], ['制造企业1', '开发商9', 30.0], ['制造企业10', '开发商1', 349.5], ['制造企业10', '开发商16', 99.0], ['制造企业10', '开发商2', 198.0], ['制造企业10', '开发商4', 541.5], ['制造企业10', '开发商7', 297.0], ['制造企业10', '开发商9', 1234.5], ['制造企业18', '开发商1', 211.5], ['制造企业18', '开发商2', 448.0], ['制造企业18', '开发商22', 49.5], ['制造企业18', '开发商4', 132.0], ['制造企业18', '开发商7', 49.5], ['制造企业18', '开发商9', 177.0], ['制造企业19', '开发商1', 106.5], ['制造企业19', '开发商16', 49.5], ['制造企业19', '开发商4', 592.5], ['制造企业19', '开发商7', 99.0], ['制造企业19', '开发商9', 655.5], ['制造企业2', '开发商1', 445.5], ['制造企业2', '开发商4', 148.5], ['制造企业3', '开发商1', 3885.0], ['制造企业3', '开发商4', 337.5], ['制造企业3', '开发商6', 49.5], ['制造企业3', '开发商9', 49.5], ['制造企业4', '开发商4', 292.5], ['制造企业4', '开发商7', 50.0], ['制造企业4', '开发商8', 250.0], ['制造企业5', '开发商1', 58.0], ['制造企业5', '开发商4', 238.6], ['制造企业5', '开发商6', 177.25], ['制造企业5', '开发商8', 439.05], ['制造企业6', '开发商1', 338.0], ['制造企业6', '开发商4', 445.9], ['制造企业6', '开发商6', 240.0], ['制造企业6', '开发商8', 200.0], ['制造企业7', '开发商1', 519.55], ['制造企业7', '开发商2', 200.0], ['制造企业7', '开发商4', 148.75], ['制造企业7', '开发商7', 198.0], ['制造企业7', '开发商9', 48.0]]
;

var color ={制造企业1:"#55efc4",制造企业3:"#81ecec",  制造企业4:"#74b9ff", 制造企业5:"#00b894", 制造企业6:"#00cec9", 制造企业7:"#0984e3", 制造企业10:"#fab1a0",制造企业18:"#fdcb6e",  制造企业19:"#e17055", 制造企业2:"#a29bfe"};
var svg = d3.select("body").append("svg").attr("width", 960).attr("height", 800);

svg.append("text").attr("x",250).attr("y",70)
	.attr("class","header").text("Sales Attempt");
	
// svg.append("text").attr("x",750).attr("y",70)
// 	.attr("class","header").text("Sales");

var g =[svg.append("g").attr("transform","translate(150,100)")
		,svg.append("g").attr("transform","translate(650,100)")];

var bp=[ viz.bP()
		.data(data)
		.min(12)
		.pad(1)
		.height(600)
		.width(200)
		.barSize(35)
		.fill(d=>color[d.primary])		
	,viz.bP()
		.data(data)
		.value(d=>d[3])
		.min(12)
		.pad(1)
		.height(600)
		.width(200)
		.barSize(35)
		.fill(d=>color[d.primary])
];
		
[0].forEach(function(i){
	g[i].call(bp[i])
	
	g[i].append("text").attr("x",-50).attr("y",-8).style("text-anchor","middle").text("制造商");
	g[i].append("text").attr("x", 250).attr("y",-8).style("text-anchor","middle").text("开发商");
	
	g[i].append("line").attr("x1",-100).attr("x2",0);
	g[i].append("line").attr("x1",200).attr("x2",300);
	
	g[i].append("line").attr("y1",610).attr("y2",610).attr("x1",-100).attr("x2",0);
	g[i].append("line").attr("y1",610).attr("y2",610).attr("x1",200).attr("x2",300);
	
	g[i].selectAll(".mainBars")
		.on("mouseover",mouseover)
		.on("mouseout",mouseout);

	g[i].selectAll(".mainBars").append("text").attr("class","label")
		.attr("x",d=>(d.part=="primary"? -30: 30))
		.attr("y",d=>+6)
		.text(d=>d.key)
		.attr("text-anchor",d=>(d.part=="primary"? "end": "start"));
	
	g[i].selectAll(".mainBars").append("text").attr("class","perc")
		.attr("x",d=>(d.part=="primary"? -100: 120))
		.attr("y",d=>+6)
		.text(function(d){ return d3.format("0.0%")(d.percent)})
		.attr("text-anchor",d=>(d.part=="primary"? "end": "end"));
});

function mouseover(d){
	[0,1].forEach(function(i){
		bp[i].mouseover(d);
		
		g[i].selectAll(".mainBars").select(".perc")
		.text(function(d){ return d3.format("0.0%")(d.percent)});
	});
}
function mouseout(d){
	[0,1].forEach(function(i){
		bp[i].mouseout(d);
		
		g[i].selectAll(".mainBars").select(".perc")
		.text(function(d){ return d3.format("0.0%")(d.percent)});
	});
}
d3.select(self.frameElement).style("height", "800px");
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
