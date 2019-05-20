<template>
<div>
  <el-row>
    <el-col :span="8"><div>
      <spray-window-chart/>
      </div></el-col>

    <el-col :span="8"><div>
     <drift-potential-chart/>
      </div></el-col>

    <el-col :span="8"><div>
       <actual-weather-chart/>
      </div></el-col>
  </el-row>
</div>
</template>

<script>
import SprayWindowChart from './components/SprayWindowChart'
import DriftPotentialChart from './components/DriftPotentialChart'
import ActualWeatherChart from './components/ActualWeatherChart'
export default {
  name: 'DashboardAdmin',
  components: {
    SprayWindowChart,
    DriftPotentialChart,
    ActualWeatherChart
  },
  data() {
    return {

   
    }
  },
  methods: {

  }
}
</script>

<style lang="scss" scoped>

</style>
