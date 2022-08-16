<script>
	export let value;
	export let min;
	export let max;
	export let precision;

	const handleChange = (e) => {
		const input = e.target.value;
		if (!isNaN(input)) {
			if (input > max) {
				value = max;
			} else if (input < min) {
				value = min;
			} else {
				if (input % 1 === 0) {
					value = input;
				} else {
					const decimalNumber = input.split('.');
					if (decimalNumber[1].length > precision) {
						const diff = precision - decimalNumber[1].length;
						value = input.slice(0, diff);
					} else {
						value = input;
					}
				}
			}
		}
	};
</script>

<div
	class="tooltip tooltip-right"
	data-tip="Max: {max ?? 'none'} |  Min: {min ?? 'none'} | Precision: {precision ?? 'none'}"
>
	<input
		type="number"
		step="1e-{precision}"
		min={min ?? ''}
		max={max ?? ''}
		bind:value
		class="input input-bordered w-full border-accent"
		on:change={handleChange}
	/>
</div>
