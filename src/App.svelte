<script>
  import Counter from "./lib/Counter.svelte";
  // import Info from "./lib/Info.svelte";
  import Product from "./lib/Product.svelte";
  import { onMount } from 'svelte';

  // props
	export let display;
  // export let setting;

  const text = 'Product title'

  const pkg = {
		name: 'svelte',
		version: 3,
		speed: 'blazing',
		website: 'https://svelte.dev'
	};


	onMount(() => {
		const interval = setInterval(() => {
			console.log('beep');
		}, 1000);

		return () => clearInterval(interval);
	});

</script>

<section class="border-dashed border-amber border-1 p-8 mb-8">

  <h1>SvelteWidget: {display}</h1>

  {#if display === 'counter'}
  <Counter />
  {/if}

  {#if display === 'thumbnail'}
  <Product {text} />
  {/if}

  <!-- <Info {...pkg} {...setting}/> -->

</section>
