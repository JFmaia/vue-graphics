<template>
  <div class="box-graph">
    <Bar id="my-chart-id" :options="chartOptions" :data="chartData" />
  </div>
</template>

<script>
import { Bar } from "vue-chartjs";
import {
  Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale,
} from "chart.js";

ChartJS.register(
  Title,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale
);

export default {
  name: "BarChart",
  components: { Bar },
  data() {
    return {
      chartData: {
        labels: ["X-box One", "PlayStation 4", "Pc Gamer"],
        datasets: [
          {
            label: "Produtos",
            data: [20, 30, 10],
            backgroundColor: "#f87979",
          },
        ],
      },
      chartOptions: {
        responsive: true,
      },
    };
  },
};
</script>

<style scoped>
.box-graph {
  padding: 20px;
  height: 500px;
  width: 700px;
}
</style>
