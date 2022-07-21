<script lang="ts">
	import { onMount } from 'svelte';
	import {
  Chart,
  BarElement,
  BarController,
  CategoryScale,
  LinearScale,
  Legend,
  Title,
  Tooltip,
  SubTitle
} from 'chart.js';

Chart.register(
  BarElement,
  BarController,
  CategoryScale,
  LinearScale,
  Legend,
  Title,
  Tooltip,
  SubTitle
);


	let ctx: any;
	onMount(async () => {
		const myChart = new Chart(ctx, {
			type: 'bar',
			data: {
				labels: ['Virtusa', 'Rangsutra', 'ISB', 'Fabindia', 'Mumbai Uni'],
				datasets: [
					{
						label: 'Years',
						data: [
							[2014, 2022],
							[2018, 2021],
							[2013, 2014],
							[2009, 2013],
							[2006, 2009]
						],
						backgroundColor: [
							'rgba(255, 134, 159, .4)',
							'rgba(98,  182, 239, .4)',
							'rgba(255, 218, 128, .4)',
							'rgba(113, 205, 205, .4)',
							'rgba(170, 128, 252, .4)'
						],
						borderWidth: 2
					}
				]
			},

			options: {
				plugins: {
					legend: {
						display: false
					}
				},
				barPercentage: 1,
				responsive: true,
				scales: {
					x: {
						ticks: {
							color: 'white',
							minRotation: 90
						}
					},
					y: {
						grid: {
							display: false
						},
						ticks: {
							color: 'white',
							callback: (value: number) => {
								return value;
							}
						},
						min: 2006,
						max: 2024
					}
				}
			}
		});
	});
</script>

<canvas id="myChart" width="200" height="400" bind:this={ctx} />
