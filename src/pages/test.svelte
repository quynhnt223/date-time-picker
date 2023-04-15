<script>
	import { onMount } from 'svelte';
	
	const cases = [
		new Date('2019-01-01T00:00:00.000Z'),
		new Date('2019-09-01T00:00:00.000Z'),
		new Date('2008-12-29T00:00:00.000Z'),
		new Date('2010-01-03T00:00:00.000Z')
	];
	
	let input;
	let check;
	
	let date = new Date();
	
	let actual = '';
	let expected = '';
	
	const pad = n => n < 10 ? `0${n}` : n;
	const ONE_WEEK = 1000 * 60 * 60 * 24 * 7;
	
	const getWeek = function(date) {
		date = new Date(date.getTime());
		date.setHours(0, 0, 0, 0);
		// Thursday in current week decides the year.
		date.setDate(date.getDate() + 3 - (date.getDay() + 6) % 7);
		// January 4 is always in week 1.
		var week1 = new Date(date.getFullYear(), 0, 4);
		// Adjust to Thursday in week 1 and count number of weeks from date to week1.
		return 1 + Math.round(((date.getTime() - week1.getTime()) / 86400000 - 3 + (week1.getDay() + 6) % 7) / 7);
	}
	
	const to_day = (date, target) => {
		const day = date.getUTCDay() || 7;
		date.setDate(date.getDate() - (day - target));
	};
	
	const week_input_value = date => {
		date = new Date(date);
		to_day(date, 4);
		
		// week 1 always contains Jan 4
		const year = date.getUTCFullYear();
		const start = new Date(year, 0, 4);
		to_day(start, 1);
		
		const elapsed = Math.floor((date - start) / (1000 * 60 * 60 * 24 * 7));
		
		return `${year}-W${pad(elapsed + 1)}`;
	};
	
	const week_input_valuex = date => {
		let year = date.getUTCFullYear();
		const start = new Date(year, 0, 1, 0, 0, 0, 0);
		start.setMinutes(start.getMinutes() - start.getTimezoneOffset());
		
		const day = start.getUTCDay() || 7;
		if (day > 4) { // Fri-Sun
			start.setDate(start.getDate() + (8 - day))
		} else {
			start.setDate(start.getDate() + (1 - day));
		}
		
		console.log(start);
		
		const elapsed = Math.floor((date - start) / ONE_WEEK);
		console.log(elapsed);
		return elapsed < 0
			? `${year - 1}-W53`
			: `${year}-W${pad(elapsed + 1)}`;
	};
	
	const run = date => {
		input.valueAsDate = date;
		update();
	};
	
	const update = e => {
		date = input.valueAsDate;
		
		check.valueAsDate = date;
		expected = check.value;
		
		actual = week_input_value(date);
	};
</script>

<input type="date" bind:this={input} on:change={update}>
<input type="week" bind:this={check}>

<div class:error="{actual !== expected}">
	<p>actual: {actual}</p>
	<p>expected: {expected}</p>
</div>

{#each cases as test}
	<button on:click="{() => run(test)}">
		{test.toISOString()}	
	</button>
{/each}

<style>
	.error {
		color: red;
	}
	
	button {
		display: block;
	}
</style>