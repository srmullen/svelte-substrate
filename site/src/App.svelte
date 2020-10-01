<script>
	import { Colors, Spacing, Typescale, Button } from 'svelte-substrate';

	const colors = [
  'gray',
  'red',
  'orange',
  'yellow',
  'green', 
  'teal',
  'blue',
  'purple',
  'pink',
];

	let color = colors[1];

	function onClick(e) {
		console.log('button click', e);
	}
</script>

<Colors />
<Spacing />
<Typescale scale={1.125} />
<main>
	<h1>Buttons</h1>
	<select bind:value={color}>
		{#each colors as color}
			<option value={color}>{color}</option>
		{/each}
	</select>
	<div class="buttons">
		<Button size="xs" variantColor={color} variant="solid" on:click={onClick}>Button</Button>
		<Button size="xs" variantColor={color} variant="ghost" on:click={onClick}>Button</Button>
		<Button size="xs" variantColor={color} variant="outline" on:click={onClick}>Button</Button>
		<Button size="xs" variantColor={color} variant="link" on:click={onClick}>Button</Button>
	</div>

	<div class="buttons">
		<Button size="sm" variantColor={color} variant="solid" on:click={onClick}>Button</Button>
		<Button size="sm" variantColor={color} variant="ghost" on:click={onClick}>Button</Button>
		<Button size="sm" variantColor={color} variant="outline" on:click={onClick}>Button</Button>
		<Button size="sm" variantColor={color} variant="link" on:click={onClick}>Button</Button>
	</div>

	<div class="buttons">
		<Button size="md" variantColor={color} variant="solid" on:click={onClick}>Button</Button>
		<Button size="md" variantColor={color} variant="ghost" on:click={onClick}>Button</Button>
		<Button size="md" variantColor={color} variant="outline" on:click={onClick}>Button</Button>
		<Button size="md" variantColor={color} variant="link" on:click={onClick}>Button</Button>
	</div>

	<div class="buttons">
		<Button size="lg" variantColor={color} variant="solid" on:click={onClick}>Button</Button>
		<Button size="lg" variantColor={color} variant="ghost" on:click={onClick}>Button</Button>
		<Button size="lg" variantColor={color} variant="outline" on:click={onClick}>Button</Button>
		<Button size="lg" variantColor={color} variant="link" on:click={onClick}>Button</Button>
	</div>

	<div class="buttons">
		<Button size="xl" variantColor={color} variant="solid" on:click={onClick}>Button</Button>
		<Button size="xl" variantColor={color} variant="ghost" on:click={onClick}>Button</Button>
		<Button size="xl" variantColor={color} variant="outline" on:click={onClick}>Button</Button>
		<Button size="xl" variantColor={color} variant="link" on:click={onClick}>Button</Button>
	</div>

	<div class="buttons">
		<Button size="md" variantColor={color} variant="solid" on:click={onClick} disabled>Button</Button>
		<Button size="md" variantColor={color} variant="ghost" on:click={onClick} disabled>Button</Button>
		<Button size="md" variantColor={color} variant="outline" on:click={onClick} disabled>Button</Button>
		<Button size="md" variantColor={color} variant="link" on:click={onClick} disabled>Button</Button>
	</div>
</main>

<style>
	.buttons :global(*) {
		margin: 8px;
	}

	:global(body) {
		font-size: 18px;
	}
</style>