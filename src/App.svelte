<script>
	import About from "./components/About.svelte";
	import Text from "./components/Text.svelte";
	import Person from "./components/Person.svelte";
	import Skills from "./components/Skills.svelte";
	import Input from "./components/Input.svelte";
	import Photos from "./components/Photos.svelte";
	import ButtonCount from "./components/ButtonCount.svelte";
	export let name;
	export let lastname;
	let svelteLogo = "https://arepa.s3.amazonaws.com/svelte-logo.png"

	const data = {
		name: "Juan",
		lastName: "Camareno",
		age:"46",
	}
</script>

<main>
	<h1>Hello {name} {lastname}!</h1>		
	<About />
	<Text anotherText="Hola!" />
	<Text />
	<Person {...data} />
	<Skills />
	<Input />
	<ButtonCount />
	<Photos />			
	<img src={svelteLogo} alt="svelte" />
</main>

<style>
	:global(body) {
		background-color: #f2eee2;
		color:#0084f6;
	}

	:global(:root){
		--theme-color:purple;
		--color-dark: #f7f7f7;
	}	

	:global(body.dark-mode, span){
		background-color: #1d3040;
		color: #bfc2c7;
		transition: background-color 300ms, color 300ms;
		--theme-color: #bfc2c7;
	}
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	main img {
		width:30%;
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