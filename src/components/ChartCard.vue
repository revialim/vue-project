<template>
    <div class="chartcard">
      <!-- <highcharts :options="chartOptions"></highcharts> -->
      <highcharts :constructor-type="'stockChart'" :options="chartOptions" ></highcharts>

      <button @click="addPoint()" key="nextbutton"> next </button>
      <!-- <button v-on:click="rescale" key="rescalebutton"> rescale </button> -->
      <button @click="setNewExtremes()"> set extremes </button>
    </div>
</template>

<script>
import { Chart } from "highcharts-vue";
import Highcharts from "highcharts";
import exportingInit from "highcharts/modules/exporting";
import stockInit from "highcharts/modules/stock";

stockInit(Highcharts);
exportingInit(Highcharts);

import chartdatajson from "../assets/chart_data.json"

// set the allowed units for data grouping
let groupingUnits = [[
    'week',             // unit name
    [1]               // allowed multiples
  ], [
    'month',
    [1]
  ]];
  
function getOhlcAndVolume(data) {
  let ohlc = [];
  let volume = [];
  let dataLength = data.length;
  for (let i = 0; i < dataLength; i += 1) {
    ohlc.push([
      data[i][0], // the date
      data[i][1], // open
      data[i][2], // high
      data[i][3], // low
      data[i][4] // close
    ]);
    volume.push([
      data[i][0], // the date
      data[i][5] // the volume
    ]);
  }
  return {
    ohlc: ohlc,
    volume: volume
  };
}
let dataOhlcVolume = getOhlcAndVolume(chartdatajson);


export default {
  name: 'ChartCard',
  props: {
  },
  components: {
    highcharts: Chart 
  },
  methods: {
    rescale: function(){
      this.chartOptions.rangeSelector.selected = 0;
    },
    addPoint: function() {
      let somedata = this.test_add_data[0].slice(0, this.test_add_data[0].length);
      this.test_add_data = this.test_add_data.slice(1, this.test_add_data.length)

      let ohls = somedata.slice(0,5);
      let volume = [somedata[0], somedata[5]];
      this.chartOptions.series[0].data.push(ohls);
      this.chartOptions.series[1].data.push(volume);
      
      this.chart.xAxis[0].setExtremes(1554048000000, somedata[0]);
    },
    setNewExtremes: function() {
      this.chart.xAxis[0].setExtremes(1554048000000, 1556812800000);
    }
  },
  data () {
    return {
      test_add_data: [[1556812800000,262,265,260.5,265,30200],
      [1557072000000,260,260,258,259,33688],
      [1557158400000,259.5,263,259,262.5,25686],[1557244800000,260,261.5,259.5,260,25902],[1557331200000,259.5,259.5,256,256.5,34167],[1557417600000,257,259,255,256,18868],[1557676800000,253,254,249.5,250.5,29318],[1557763200000,247.5,251,245,248.5,45621],[1557849600000,251,252,249,249,37223],[1557936000000,248.5,249.5,246,247,30332],[1558022400000,249,249,241.5,241.5,40007],[1558281600000,242.5,243,238,238,47098],[1558368000000,233.5,236,232.5,234,82873],[1558454400000,236.5,240.5,235.5,238,36289],[1558540800000,233.5,233.5,230,230,62259],[1558627200000,230,234,230,233,38227],[1558886400000,234,235,231,231,37447],[1558972800000,232,232,230.5,230.5,99322],[1559059200000,228,230.5,227,229.5,32260],[1559145600000,230,231.5,229,231,40375],[1559232000000,232,237.5,231,235.5,49163],[1559491200000,235.5,238.5,232,238,36687],[1559577600000,237.5,238,233,233,24443],[1559664000000,238,238,234,235,35902],[1559750400000,231.5,232,229.5,232,34652],[1560096000000,237.5,240,234.5,240,35374]
      ],
      chartOptions: {
        chart: {
          events: {
            load: (function(self) {
              return function() {
                self.chart = this; // saving chart reference in the component
              };
            })(this)
          }
        },
        rangeSelector: {
          // selected: 1
        },
        title: { text: 'Some Title' },
        yAxis: [{
          labels: {
            align: 'right',
            x: -3
          },
          title: {
            text: 'OHLC'
          },
          height: '60%',
          lineWidth: 2,
          resize: {
            enabled: true
          }
        }, {
          labels: {
            align: 'right',
            x: -3
          },
          title: {
            text: 'Volume'
          },
          top: '65%',
          height: '35%',
          offset: 0,
          lineWidth: 2
        }],
        xAxis: {
			    // min: new Date (1454739200000),
          // max: new Date(1456726400000)
        },
        time: {
            useUTC: false
        },
        exporting: {
            enabled: false
        },
        tooltip: { split: true },
        series:
          [{
            type: 'candlestick',
            name: 'AAPL',
            data: dataOhlcVolume.ohlc,
            // dataGrouping: {
            //   units: groupingUnits
            // }
          }, {
            type: 'column',
            name: 'Volume',
            data: dataOhlcVolume.volume,
            yAxis: 1,
            // dataGrouping: {
            //   units: groupingUnits
            // }
          }]
      }
    }
  }
}
</script>

<style lang="sass" scoped>
  .chartcard
    padding: 2em
    background-color: #222

</style>
