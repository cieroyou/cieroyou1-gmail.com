<template>
    <canvas id="myBarChart" width="400" height="400" ref="barChart"></canvas>
</template>

<script>
import Chart from 'chart.js';
export default {
 mounted() {
    // chart.js 예제 :https://www.chartjs.org/docs/latest/getting-started/usage.htm
    // const ctx = document.getElementById('myBarChart'); 
    const ctx = this.$refs.barChart;
    // 예시에서 Jquery 를 통해 DOM에 접근한 후 조작이 이뤄지므로, Vue 에서는 DOM 이 생성되고 난 후인 mounted() 라이프사이클 훅에 넣어준다.
    var myBarChart = new Chart(ctx, {
        type: 'bar',
        data: {
            labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
            datasets: [{
                label: '# of Votes',
                data: [12, 19, 3, 5, 2, 3],
                backgroundColor: [
                    'rgba(255, 99, 132, 0.2)',
                    'rgba(54, 162, 235, 0.2)',
                    'rgba(255, 206, 86, 0.2)',
                    'rgba(75, 192, 192, 0.2)',
                    'rgba(153, 102, 255, 0.2)',
                    'rgba(255, 159, 64, 0.2)'
                ],
                borderColor: [
                    'rgba(255, 99, 132, 1)',
                    'rgba(54, 162, 235, 1)',
                    'rgba(255, 206, 86, 1)',
                    'rgba(75, 192, 192, 1)',
                    'rgba(153, 102, 255, 1)',
                    'rgba(255, 159, 64, 1)'
                ],
                borderWidth: 1
            }]
        },
        options: {
            scales: {
                yAxes: [{
                    ticks: {
                        beginAtZero: true
                    }
                }]
            }
        }
    });
  console.log(myBarChart);
  }
}
</script>

<style>

</style>