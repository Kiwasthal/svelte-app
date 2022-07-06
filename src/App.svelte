<script>
	import {setContext} from 'svelte'
	import Outer from './components/Outer.svelte';
	import Button from './components/Button.svelte'
	import ComponentC from './components/ComponentC.svelte'
	import Popup from './components/Popup.svelte'

	let showPopup = false
	const userName = 'Steerpike'

	let closePopup = (e) => {
		showPopup = false
		console.log(e.detail);
	}

	let handleGreet = (e) => alert(e.detail)
	

	//It's good practice not to use string values as the context key but rather an object because different component libraries might accidentally use the same key, while using an object literal the keys will not conflict under any circumstances since object's have referential equality.
	
	setContext('username-context', userName)
	// import Greet from "./components/greet.svelte";
	// const name = 'Steerpike'
	// const github = 'Kiwasthal'
	// const obj = {
	// 	name  : 'Fuchsia',
	// 	title : 'Princess'
	// }

	// const name = 'Steerpike'
	// const github = '<b>Kiwasthal</b>'
	// //When using the @html prefix you should only render
	// //The content that you trust
	// const headingId = 'heading'
	// const disabled = false
	// const status = 'success'
	// const promoted = true
	// //Conditional binding in case variable and class name do not align
	// //isPromoted = true

	// //Conditional Rendering
	// const num = 'Text'

	// //List rendering
	// const names = ['Sepulchrave' , 'Prunesquellor', 'Fuchsia']
	// const fullNames =[
	// 	{first : 'Mervyn' , last: 'Peake'},
	// 	{first : 'Edward', last : 'Dunsanny'},
	// 	{first : 'Ursula' , last : 'LeGuin'}
	// ]
	// //Event Handling
	// let count = 0
	// let handleClick = (e,stepSize) => {
	// 	console.log(e);
	// 	count += stepSize
	// } 

	// const  formValues = {
	// 	name : '',
	// 	profileSummary : '',
	// 	country : '',
	// 	jobLocation : [],
	// 	remoteWork : false,
	// 	skillSet : [],
	// 	yearsOfExperience : '',
	// }

	// const submitForm =(e) => 
	// 	console.log(formValues)
	

 	// let firstName = 'Mervyn'
	// let lastName = 'Peake'
	// $: fullName = `${firstName} ${lastName}`
	// $: {
	// 	const greet = `Fullname is ${firstName} ${lastName}`
	// 	console.log(greet)
	// }

	// let volume = 0
	// $: {
	// 	if (volume < 0) {
	// 		alert('can\'t go lower than 0')
	// 		volume = 0
	// 	} else if (volume > 20) {
	// 		alert('can\'t go higher than 20')
	// 		volume = 20
	// 	}
	// }

	// let items = [
	// 	{
	// 		id : 1 ,
	// 		title : 'TV',
	// 		price : 100,
	// 	} ,
	// 	{
	// 		id : 2,
	// 		title : 'Phone',
	// 		price : 200,
	// 	},
	// 	{
	// 		id : 3,
	// 		title : 'Laptop', 
	// 		price : 300,
	// 	}
	// ]

	// $:total  = items.reduce((total , curItem) => (total = total + curItem.price) , 0)


</script>

<main>
	<Outer on:greet={handleGreet} />
	<Button on:click={() => {
		alert('Clicked')
	}} />
	<button on:click={
		() => showPopup = true
	}>Show Popup</button>
	{#if showPopup}
		<Popup  on:close={ closePopup} />	
	{/if}

	<h2>App component username - {userName}</h2>
	<ComponentC />
	<!-- <Greet name='Steerpike' title='Main' />
	<Greet name='Titus' title='Heir'/>
	<Greet name='Slugg' title='Nanny'/>
	<Greet {name} />
	<Greet {...obj} /> -->


	<!-- <h2>Current volume {volume}</h2>
	<button on:click={() => {
		volume = volume +1
	}} >Increase volume</button>
	<button on:click={() => {
		volume = volume -1
	}}>Decrease volume</button>
	When working with arrays or objects direct mutation will not cause a rerender -->
	<!-- <button on:click={() => {
		firstName = 'Ursula'
		lastName = 'LeGuin'
	}} >Change name</button>
	<h2>{firstName} {lastName}</h2>
	<h2>{fullName}</h2>

	<button on:click={() => (items = [...items,{id : 4, title : 'Keyboard' , price : 50} ] )}>Add item</button>
	<h2>
		Total - {total}
	</h2> --> 
	<!-- <h2 class="underline">Underlined Text</h2>
	<h2 class={status}>Status</h2>
	<h2 class:promoted >Movie Title</h2> -->
	<!-- <h2 class:promoted={isPromoted}>Movie tag</h2> -->
	<!-- <h1>Hello {name}</h1>
	<div>{@html github}</div>
	<h2 id={headingId}>This is a heading</h2>
	<button {disabled}>Bind</button> -->
	<!-- {#if num===0}
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
	{/each} -->
	<!-- Inline f definition for simple handling -->
	<!-- <button on:click={() => (count = count + 1)}>Count {count}</button> -->
	<!-- <button on:click={(e) =>  handleClick(e,5)}>Count {count}</button>
	<button on:click={(e) =>  handleClick(e,10)}>Count {count}</button> -->
	<!-- <div>
		<pre>
			{JSON.stringify(formValues , null , 2)}
		</pre>
	</div>
	<form on:submit|preventDefault={submitForm}>
		<div>
			<label for="name">Name</label>
			<input type="text"  id="name" bind:value={formValues.name} />
		</div>
		<div>
			<label for="profile">Profile Summary</label>
			<textarea  id="profile" bind:value={formValues.profileSummary} />
		</div>
		<div>
			<label for="country">Country</label>
			<select id="country" bind:value={formValues.country}>
				<option value="">Select a country</option>
				<option value="india">India</option>
				<option value="vietnam">Vietnam</option>
				<option value="singapore">Singapore</option>
			</select>
		</div>
		<div>
			<label for="job-location">Job Location</label>
			<select id="job-location" bind:value={formValues.jobLocation} multiple>
				<option value="">Select a country</option>
				<option value="india">India</option>
				<option value="vietnam">Vietnam</option>
				<option value="singapore">Singapore</option>
			</select>	
		</div>
		<div>
			<input type="checkbox" id="remoteWork"  bind:checked={formValues.remoteWork}/>
			<label for="remoteWork">Open for remote work?</label>
		</div>
		<div>
			<label>Skill set</label>
			<input type="checkbox" id="html" value="html" bind:group={formValues.skillSet}/>
			<label for="html">HTML</label>
			<input type="checkbox" id="css" value="css" bind:group={formValues.skillSet}/>
			<label for="css">CSS</label>
			<input type="checkbox" id="javascript" value="javascript" bind:group={formValues.skillSet}/>
			<label for="javascript">JavaScript</label>
		</div>
		<div>
			<label>Years of Experience</label>
			<input type="radio" id="0-2" value="0-2" bind:group={formValues.yearsOfExperience}/>
			<label for="0-2">0-2</label>
			<input type="radio" id="3-5" value="3-5" bind:group={formValues.yearsOfExperience}/>
			<label for="3-5">3-5</label>
			<input type="radio" id="6-10" value="6-10" bind:group={formValues.yearsOfExperience}/>
			<label for="6-10">6-10</label>
			<input type="radio" id="10+" value="10+" bind:group={formValues.yearsOfExperience}/>
			<label for="10+">10+</label>
		</div>
		<div>
			<button type="submit">Submit</button>
		</div>
	</form> -->
</main>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    
<style>
	/* .underline {
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
	} */

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}
/* 
	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	} */

	/* input + label {
		display: inline-flex;
	} */

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>