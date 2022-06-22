<template>
  <div id="app">
    <ejs-chart :primaryXAxis="chartPrimaryXAxis" :primaryYAxis="chartPrimaryYAxis" :title="chartTitle">  
      <e-series-collection>
        <e-series type="Line" :dataSource="chartData" xName="date" yName="value" 
        :marker="chartMarker">
        </e-series>
      </e-series-collection>   
    </ejs-chart>
  </div>
</template>

<script>
import Vue from "vue";
import { ChartPlugin, LineSeries, DateTime, Logarithmic } from '@syncfusion/ej2-vue-charts';
Vue.use(ChartPlugin);

export default {
  provide : {
    chart : [LineSeries, DateTime, Logarithmic]
  },
  data() {
    return {
      chartMarker : {
        visible : true,
        height : 7,
        width : 7
      },
      chartTitle : 'Product Growth',
      chartPrimaryXAxis : {
        valueType : 'DateTime',
        title : 'Date',
        edgeLabelPlacement : 'Shift'
      },
      chartPrimaryYAxis : {
        valueType : 'Logarithmic',
        title : 'Profit',
        minimum : 1,
        maximum : 1000000,
        interval : 2,
        logBase : 2,
        labelFormat : '$ {value}'
      },
      chartData : [
         { date : new Date('2011, 1, 1'), value : 80 },
         { date : new Date('2012, 1, 1'), value : 200 },
         { date : new Date('2013, 1, 1'), value : 400 },
         { date : new Date('2014, 1, 1'), value : 600 },
         { date : new Date('2015, 1, 1'), value : 700 },
         { date : new Date('2016, 1, 1'), value : 1400 },
         { date : new Date('2017, 1, 1'), value : 2000 },
         { date : new Date('2018, 1, 1'), value : 4000},
         { date : new Date('2019, 1, 1'), value : 6000 },
         { date : new Date('2020, 1, 1'), value : 8000 },
         { date : new Date('2021, 1, 1'), value : 11000 }
      ]

    };
  }
}
</script>

