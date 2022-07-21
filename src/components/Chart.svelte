<script lang="ts">
	import { onMount } from 'svelte';
    import Chart from 'chart.js/auto';

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
						backgroundColor: ['rgba(29, 26, 25,0.8)'],
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
				barPercentage: 0.5,
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
							callback: (value:number) => {
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
