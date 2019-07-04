<template>
  <div class="dashboard-editor-container">
<el-row>
  <div class="chart-wrapper">
    <entity />
  </div>
</el-row>
<el-row :gutter="32">
  <el-col :xs="24" :sm="24" :lg="16">
    <div class="chart-wrapper">
      <line-chart />
    </div>
  </el-col>
</el-row>



  </div>

</template>

<script>

import LineChart from './components/LineChart'

import Entity from './components/Entity'


export default {
  name: 'DashboardAdmin',
  components: {

    LineChart,

    Entity
  },
  data() {

  },
  mounted() {

  },
  methods: {

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
