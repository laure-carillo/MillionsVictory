<script>
	export let value;
	export let min;
	export let max;

	const handleChange = (e) => {
		const input = e.target.value;
		if (!isNaN(input)) {
			if (input > max) {
				value = max;
			} else if (input < min) {
				value = min;
			} else {
				value = input;
			}
		}
	};
</script>

<div class="tooltip tooltip-right" data-tip="Max: {max ?? 'none'} |  Min: {min ?? 'none'} ">
	<input
		type="number"
		step="1"
		min={min ?? ''}
		max={max ?? ''}
		bind:value
		class="input input-bordered w-full border-accent"
		on:change={handleChange}
	/>
</div>
