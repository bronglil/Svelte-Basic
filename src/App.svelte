<script>
	export let name;
	let beltColour = "Black"
	let firstName = "";
	let lastName = "";


	// Reactive values

	$: fullName = `${firstName} - ${lastName}`

	const handleClikc = () => {
		if(beltColour === 'Black'){
			beltColour = "Dark Blue"
		}else{
			beltColour = "Black"
		}
	}

	const handleInputData = (e) => {
		const text = e?.target?.value;
		beltColour = text;
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<p class="beltColor">{fullName} (Belt Color is {beltColour}) </p>

	<button on:click={()=>handleClikc()}>Change Color</button>
	<!-- <input type="text" on:input={handleInputData} value={beltColour}/> -->
	<input type="text" bind:value={firstName}/>
	<input type="text" bind:value={lastName}/>
	<input type="text" bind:value={beltColour}/>

</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	.beltColor {
		color: #0f3a72;
		text-transform: uppercase;
		font-size: 4em;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>