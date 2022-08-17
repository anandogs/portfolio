<script lang="ts">
	import { onMount } from 'svelte';
    import { Chart, registerables } from 'chart.js/dist/chart.esm';
	Chart.register(...registerables);
	let ctx: any;
    const workEx = ['\nCorporate MIS (2018 - Present: Part-time)\nFinance Partner (2019 - 2019: Full-time)\nFinancial Processes (2014-2018: Full-time)\n', '\nEcommerce Consultant (2018-2021:Part-time)\n', '\nEcommerce Executive (2011 - 2013)\nExecutive Assistant (2009-2011)\n']
	onMount(async () => {
		const myChart = new Chart(ctx, {
			type: 'bar',
			data: {
				labels: ['Virtusa', 'Rangsutra', 'Fabindia'],
				datasets: [
					{
						label: 'Years',
						data: [
							[2014, 2022],
							[2018, 2021],
							[2009, 2013],
						],
						backgroundColor: [
							'rgba(255, 134, 159, .4)',
							'rgba(98,  182, 239, .4)',
							'rgba(113, 205, 205, .4)',
						],
						borderWidth: 2
					}
				]
			},

			options: {
                animation: {
            duration: 3000,
        },
				plugins: {
                    tooltip:{
                        callbacks: {
                            afterTitle: function(context:any) {
                                return workEx[context[0].dataIndex]
                            },
             

                            
                        }
                    },
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
<canvas id="myChart" width="50" height="50" bind:this={ctx} />