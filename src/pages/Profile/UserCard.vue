<template>
  <card type="user">
    <p class="card-text">
    </p>
    <div class="author">
      <div class="block block-one"></div>
      <div class="block block-two"></div>
      <div class="block block-three"></div>
      <div class="block block-four"></div>
      <a href="#">
        <img class="avatar" src="img/anime3.png" alt="...">
        <h5 class="title">{{user.fullName}}</h5>
      </a>
      <p class="description">
        {{user.title}}
      </p>
    </div>
    <p class="card-description">
      {{user.description}}
    </p>

    <card type="chart">
        <template slot="header">
        <h5 class="card-category">Total Air yang diminum</h5>
        <h3 class="card-title"><i class="tim-icons icon-bell-55 text-primary "></i> 763,215</h3>
        </template>
        <div class="chart-area">
        <line-chart style="height: 100%"
                    :chart-data="user.chart.chartData"
                    :gradient-colors="user.chart.gradientColors"
                    :gradient-stops="user.chart.gradientStops"
                    :extra-options="user.chart.extraOptions">
        </line-chart>
        </div>
    </card>
  </card>
</template>
<script>
    import LineChart from '@/components/Charts/LineChart';
    import BarChart from '@/components/Charts/BarChart';
    import * as chartConfigs from '@/components/Charts/config';
  
  export default {
    components: {
      LineChart,
      BarChart
    },
    props: {
      user: {
        type: Object,
        default: () => {
          return {};
        }
      }
    }
  }
</script>
<style>
</style>
