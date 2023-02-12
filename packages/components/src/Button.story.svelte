<script lang="ts">
	import type { Hst } from '@histoire/plugin-svelte';
	import Button from './Button.svelte';
	import { logEvent } from 'histoire/client';

	export let Hst: Hst;

	let content = 'Click me!';
</script>

<Hst.Story>
	<svelte:fragment slot="controls">
		<Hst.Text bind:value={content} title="Content" />
	</svelte:fragment>

	<Button on:click={(event) => logEvent('Click', event)}>
		{content}
	</Button>
</Hst.Story>
