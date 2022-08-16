<script>
	export let value;
	export let desc;
</script>

<div data-tip="Desc :{desc ?? 'none'}">
	<label class="label cursor-pointer">
		<input type="checkbox" class="toggle toggle-accent" bind:checked={value} />
	</label>
</div>
