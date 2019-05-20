<template>
  <div class="dashboard-editor-container">
    <span>Application Product</span>
  <el-select v-model="value" placeholder="Select Product">
    <el-option
      v-for="item in options"
      :key="item.value"
      :label="item.label"
      :value="item.value">
    </el-option>
  </el-select>
  <br/>
 <span class="demonstration">Application Date</span>
    <el-date-picker
      type="dates"
      v-model="appDate"
      placeholder="Pick one or more dates">
    </el-date-picker>
    <br/>
    <span>Application Rate & Volume</span>
      <el-input-number v-model="numRate" controls-position="right" :min="0.001"  :max="10" :step="0.001"></el-input-number>
      <el-switch
  v-model="rateUnit"
  active-text="%"
  inactive-text="V">
</el-switch>
      <el-input-number v-model="numVolume" controls-position="right" :min="0.001" :max="10" :step="0.001"></el-input-number>
      <el-switch
  v-model="volumeUnit"
  active-text="L"
  inactive-text="g">
</el-switch>
<el-card class="box-card">
  <div slot="header" class="clearfix">
    <span>Recommendation</span>
    
  </div>
recommendation content
</el-card>
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
      lineChartData: lineChartData.newVisitis,
      appDate:undefined,
       options: [{
          value: 'value1',
          label: 'product1'
        }, {
          value: 'value2',
          label: 'product2'
        }, {
          value: 'value3',
          label: 'product3'
        }, {
          value: 'value4',
          label: 'product4'
        }, {
          value: 'value5',
          label: 'product5'
        }],
        value: '',
        numRate:0.001,
        numVolume:0.001,
        rateUnit:true,
        volumeUnit:true
    }
  },
  methods: {
    handleSetLineChartData(type) {
      this.lineChartData = lineChartData[type]
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
  .box-card{
        width: 480px;
  }
}
</style>
