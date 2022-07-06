<script>

  	const names =[
		{first : 'Mervyn' , last: 'Peake'},
		{first : 'Edward', last : 'Dunsanny'},
		{first : 'Ursula' , last : 'LeGuin'}
	]
</script>

{#each names as name (name)}
  <slot name="author" first={name.first} last={name.last} />
{/each}