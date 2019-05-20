<template>
<el-table
      :data="tableData"
      style="width: 100%">
      <el-table-column
        prop="date"
        label="Date"
        width="180">
      </el-table-column>
      <el-table-column
        prop="maxTemp"
        label="Max Temp"
        width="180">
      </el-table-column>
      <el-table-column
        prop="minTemp"
        label="Min Temp">
      </el-table-column>
        <el-table-column
        prop="avgTemp"
        label="AVG Temp">
      </el-table-column>
    </el-table>
</template>

<script>

import faker from 'faker';


export default {
  props: {
    
  },
  data() {
    return {
    tableData: [{
            date: '2016-05-03',
            maxTemp: '2',
            minTemp: '1',
            avgTemp:"something"
          }, {
            date: '2016-05-02',
            maxTemp: 'Tom',
            minTemp: 'No. 189, Grove St, Los Angeles',
            avgTemp:"something"
          }, {
            date: '2016-05-04',
            maxTemp: 'Tom',
            minTemp: 'No. 189, Grove St, Los Angeles',
            avgTemp:"something"
          }, {
            date: '2016-05-01',
            maxTemp: 'Tom',
            minTemp: 'No. 189, Grove St, Los Angeles',
            avgTemp:"something"
          }]
  
        
    }
  },
  created(){
      const generateRow =()=>{
          return {
              date:faker.date.past().toLocaleDateString(),
              maxTemp:faker.random.number(),
              minTemp:faker.random.number(),
              avgTemp:faker.random.number()
          }
      }
      const generateTable = (n)=>{
          let table =[];
          for(let i=0;i<n;i++)
            table.push(generateRow())
        return table;
      }
      //generate data
      this.tableData = generateTable(10);
  },
  mounted() {},
  beforeDestroy() { },
  methods: {}
}
</script>
