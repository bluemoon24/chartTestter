<template>
  <v-container>
    <v-layout text-xs-center wrap column>
      <v-flex xs12>
        <div ref="chart" style="height:600px; width:600px">
        </div>
        <v-textarea
          outline
          @input="draw"
         >
        </v-textarea>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import roiCharts from 'roi-charts'

export default {
  data: () => ({
    chartConfig: ''
  }),

  mounted() {
    console.log('mounted with roi-charts version', roiCharts.version)
  },

  methods: {
    draw: function (newval) {
      let config = JSON.parse(newval)
      console.log('drawing', config)
      roiCharts.smallMultiples({container: this.$refs.chart, ...config})
    }
  }
}

</script>

<style>

</style>
