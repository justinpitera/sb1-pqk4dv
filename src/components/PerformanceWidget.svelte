<script lang="ts">
  import { Bar } from 'svelte-chartjs';
  import {
    Chart as ChartJS,
    CategoryScale,
    LinearScale,
    BarElement,
    Title,
    Tooltip,
    Legend
  } from 'chart.js';

  ChartJS.register(
    CategoryScale,
    LinearScale,
    BarElement,
    Title,
    Tooltip,
    Legend
  );

  const data = {
    labels: ['API Response', 'DB Queries', 'Cache Hits', 'Processing'],
    datasets: [
      {
        label: 'Average Time (ms)',
        data: [250, 180, 50, 120],
        backgroundColor: 'rgba(54, 162, 235, 0.5)',
        borderColor: 'rgb(54, 162, 235)',
        borderWidth: 1
      }
    ]
  };

  const options = {
    responsive: true,
    maintainAspectRatio: false,
    plugins: {
      legend: {
        position: 'top' as const,
        labels: {
          color: '#fff'
        }
      }
    },
    scales: {
      y: {
        grid: {
          color: 'rgba(255, 255, 255, 0.1)'
        },
        ticks: {
          color: '#fff'
        }
      },
      x: {
        grid: {
          color: 'rgba(255, 255, 255, 0.1)'
        },
        ticks: {
          color: '#fff'
        }
      }
    }
  };
</script>

<div class="h-[300px]">
  <Bar {data} {options} />
</div>