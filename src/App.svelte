<script>
	const name = 'Steerpike'
	const github = '<b>Kiwasthal</b>'
	//When using the @html prefix you should only render
	//The content that you trust
</script>

<main>
	<h1>Hello {name}</h1>
	<div>{@html github}</div>
</main>

<style>
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