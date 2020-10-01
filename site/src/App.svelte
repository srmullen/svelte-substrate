<script>
	import { Colors, Spacing, Typescale, Button, Input } from 'svelte-substrate';

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

	let color = colors[5];

	function onClick(e) {
		console.log('button click', e);
	}
</script>

<Colors />
<Spacing />
<Typescale scale={1.125} />
<main>
	<div>
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
	</div>
	<div>
		<h1>Inputs</h1>
		<div class="inputs">
			<h5>Small</h5>
			<Input size="sm" placeholder="Outline Variant" variant="outline" variantColor={color} />
			<Input size="sm" placeholder="Filled Variant" variant="filled" variantColor={color} />
			<Input size="sm" placeholder="Flushed Variant" variant="flushed" variantColor={color} />
			<Input size="sm" placeholder="Unstyled Variant" variant="unstyled" variantColor={color} />
		</div>

		<div class="inputs">
			<h5>Medium</h5>
			<Input size="md" placeholder="Outline Variant" variant="outline" variantColor={color} />
			<Input size="md" placeholder="Filled Variant" variant="filled" variantColor={color} />
			<Input size="md" placeholder="Flushed Variant" variant="flushed" variantColor={color} />
			<Input size="md" placeholder="Unstyled Variant" variant="unstyled" variantColor={color} />
		</div>

		<div class="inputs">
			<h5>Large</h5>
			<Input size="lg" placeholder="Outline Variant" variant="outline" variantColor={color} />
			<Input size="lg" placeholder="Filled Variant" variant="filled" variantColor={color} />
			<Input size="lg" placeholder="Flushed Variant" variant="flushed" variantColor={color} />
			<Input size="lg" placeholder="Unstyled Variant" variant="unstyled" variantColor={color} />
		</div>
	</div>

	<div class="inputs">
			<h5>disabled</h5>
			<Input placeholder="Outline Variant" variant="outline" variantColor={color} disabled={true} />
			<Input placeholder="Filled Variant" variant="filled" variantColor={color} disabled={true} />
			<Input placeholder="Flushed Variant" variant="flushed" variantColor={color} disabled={true} />
			<Input placeholder="Unstyled Variant" variant="unstyled" variantColor={color} disabled={true} />
		</div>
</main>

<style>
	:global(body) {
		font-size: 18px;
	}

	.buttons :global(*) {
		margin: 8px;
	}

	.inputs :global(*) {
		margin-bottom: var(--s2);
	}
</style>