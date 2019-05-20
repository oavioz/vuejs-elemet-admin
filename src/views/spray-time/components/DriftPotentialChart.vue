<template>
  <highcharts :options="chartOptions"></highcharts>
</template>

<script>




export default {
  props: {
    
  },
  data() {
    return {
    chartOptions: {
            chart: {
                renderTo: 'container',
                type: 'pie'
            },
                  credits: {
        enabled: false
    },
            title: {
                text: 'Drift Potential'
            },
            yAxis: {
                title: {
                    text: 'Total percent market share'
                }
            },
            plotOptions: {
                pie: {
                    shadow: false
                }
            },
            tooltip: {
                formatter: function() {
                    return '<b>'+ this.point.name +'</b>: '+ this.y +' %';
                }
            },
            series: [{
                name: 'Browsers',
                data: [["Firefox",6],["MSIE",4],["Chrome",7]],
                size: '60%',
                innerSize: '80%',
                showInLegend:true,
                dataLabels: {
                    enabled: false
                }
            }]
        }
    }
  },
  mounted() {},
  beforeDestroy() { },
  methods: {}
}
</script>
