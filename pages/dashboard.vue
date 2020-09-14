<template>
  <section>
    <v-toolbar color="transparent" flat dense dark>
      <v-toolbar-title> Dashboard </v-toolbar-title>
    </v-toolbar>

    <v-row class="px-4">
      <v-col lg="6" md="12">
        <v-card height="395px">
          <v-card-title> Total Earnings </v-card-title>
          <v-card-text>
            <area-chart :data="chartData"></area-chart>
          </v-card-text>
        </v-card>
      </v-col>
      <v-col class="py-0">
        <v-row>
          <v-col md="6" sm="6" xs="12" v-for="n in 4" :key="n">
            <v-card>
              <v-card-title> Revenue </v-card-title>
              <v-card-text>
                <h5 class="text-h5 black--text text-center">$123.00</h5>
                <v-sparkline
                  class="mt-4"
                  :value="value"
                  :gradient="gradient"
                  :smooth="radius || false"
                  :padding="padding"
                  :line-width="width"
                  :stroke-linecap="lineCap"
                  :gradient-direction="gradientDirection"
                  :fill="fill"
                  :type="type"
                  :auto-line-width="autoLineWidth"
                  auto-draw
                ></v-sparkline>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </section>
</template>

<script>
const gradients = [
  ['#222'],
  ['#42b3f4'],
  ['red', 'orange', 'yellow'],
  ['purple', 'violet'],
  ['#00c6ff', '#F0F', '#FF0'],
  ['#f72047', '#ffd200', '#1feaea'],
]
export default {
  data: () => ({
    chartData: {
      1: Math.random() * 100,
      2: Math.random() * 100,
      3: Math.random() * 100,
      4: Math.random() * 100,
      5: Math.random() * 100,
      6: Math.random() * 100,
      7: Math.random() * 100,
      8: Math.random() * 100,
      9: Math.random() * 100,
      10: Math.random() * 100,
    },
    width: 2,
    radius: 10,
    padding: 8,
    lineCap: 'round',
    gradient: gradients[5],
    value: [0, 2, 5, 9, 5, 10, 3, 5, 0, 0, 1, 8, 2, 9, 0],
    gradientDirection: 'top',
    gradients,
    fill: false,
    type: 'trend',
    autoLineWidth: false,
  }),
}
</script>
