<script>
	export let value;
        let handleChange = (e) => {
        const userInput = e.target.value;
        const dateInLocale = new Date(userInput);
        const clientOffset = dateInLocale.getTimezoneOffset();
        const inputInUTCMs = dateInLocale.getTime() - clientOffset * 60000;
        value = new Date(inputInUTCMs).toISOString();
        inputString = value.slice(0, -8);
</script>

<input type="time" bind:value class="input input-bordered w-full border-accent" />
