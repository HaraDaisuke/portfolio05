<template>
    <v-container>
        <v-row>
            <v-col cols="4">
                <Radar :data="chartData_lang" :options="chartOptions" />
            </v-col>
            <v-col cols="4">
                <Radar :data="chartData_front" :options="chartOptions" />
            </v-col>
            <v-col cols="4">
                <Radar :data="chartData_back" :options="chartOptions" />
            </v-col>
        </v-row>
    </v-container>
</template>

<script setup>
import {
  Chart as ChartJS,
  RadialLinearScale,
  PointElement,
  LineElement,
  Filler,
  Tooltip,
  Legend
} from 'chart.js'
import { Radar } from 'vue-chartjs'
import { ref } from 'vue'
import * as chartConfig from '../plugins/chartConfig'

ChartJS.register(
  RadialLinearScale,
  PointElement,
  LineElement,
  Filler,
  Tooltip,
  Legend
)

const chartData_lang = ref(chartConfig.data_lang)
const chartData_front = ref(chartConfig.data_front)
const chartData_back = ref(chartConfig.data_back)
const chartOptions = ref(chartConfig.options)
</script>
