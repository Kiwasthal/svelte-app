<script>
	const name = 'Steerpike'
	const github = '<b>Kiwasthal</b>'
	//When using the @html prefix you should only render
	//The content that you trust
	const headingId = 'heading'
	const disabled = false
	const status = 'success'
	const promoted = true
	//Conditional binding in case variable and class name do not align
	//isPromoted = true

	//Conditional Rendering
	const num = 'Text'

	//List rendering
	const names = ['Sepulchrave' , 'Prunesquellor', 'Fuchsia']
	const fullNames =[
		{first : 'Mervyn' , last: 'Peake'},
		{first : 'Edward', last : 'Dunsanny'},
		{first : 'Ursula' , last : 'LeGuin'}
	]
	//Event Handling
	let count = 0
	let handleClick = (e,stepSize) => {
		console.log(e);
		count += stepSize
	} 
</script>

<main>
	<h2 class="underline">Underlined Text</h2>
	<h2 class={status}>Status</h2>
	<h2 class:promoted >Movie Title</h2>
	<!-- <h2 class:promoted={isPromoted}>Movie tag</h2> -->
	<h1>Hello {name}</h1>
	<div>{@html github}</div>
	<h2 id={headingId}>This is a heading</h2>
	<button {disabled}>Bind</button>
	{#if num===0}
		<h2>The number is zero</h2>
		{:else if num < 0}
		<h2>The number is negative</h2>
		{:else if num > 0}
		<h2>The number is positive</h2>
		{:else}
		<h2>Not a number</h2>
	{/if}
	{#each names as name, index (name)}
		<h2>{index + 1} {name}</h2>
	{/each}
	{#each fullNames as name , index (name.first)}
	<h2>{index +1} {name.first} {name.last}</h2>
	{/each}
	<!-- Inline f definition for simple handling -->
	<!-- <button on:click={() => (count = count + 1)}>Count {count}</button> -->
	<button on:click={(e) =>  handleClick(e,5)}>Count {count}</button>
	<button on:click={(e) =>  handleClick(e,10)}>Count {count}</button>
</main>

<style>
	.underline {
		text-decoration: underline;
	}

	.danger {
		color : red
	}

	.success {
		color : olive
	}

	.promoted {
		font-style: italic;
	}

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
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