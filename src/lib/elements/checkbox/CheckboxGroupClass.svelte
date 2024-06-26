<script lang="ts">
	// @ts-nocheck

	import CheckboxSingle from './CheckboxSingle.svelte';
	// on page where is form with checkboxes we need add arrays of data like this:

	// const desktop = ['Mac Studio', 'Mac Mini', 'iMac', 'Mac Pro'];
	// const mobile = ['Macbook', 'iPad', 'iPhone'];
	// implement checkboxes Group will be like this:

	// <Form>
	// <CheckboxGroupClass group="Apple Desktop" data={desktop} />
	// <CheckboxGroupClass group="Mobile" data={mobile} />
	// </Form>

	interface Props {
		data: string[];
		group: string;
	}

	const { data, group }: Props = $props();

	$effect(() => {
		const checkboxCroups = [...document.querySelectorAll('.checkbox-group')];
		checkboxCroups.forEach((group: any) => {
			const inputs = [...group.querySelectorAll('input')];
			inputs.forEach((el: any) => {
				(el as HTMLInputElement).checked = false;
			});
		});
	});

	function checkForSelected(e: { target: HTMLInputElement }) {
		const tar = e.target;
		const isParent = tar.hasAttribute('data-parent');
		updateChecks(tar.name, isParent);
	}

	function updateChecks(name: string, isParent = false) {
		if (name) {
			const parent = document.querySelector(`[name="${name}"][data-parent]`);
			const children = [...document.querySelectorAll(`[name="${name}"][data-child]`)];
			const checked = children.filter((el) => el.checked);
			const notAllChecked = checked.length < children.length;

			if (isParent) {
				Array.from(children).forEach((el: HTMLInputElement) => {
					el.checked = notAllChecked;
				});
			} else if (parent) {
				parent.checked = !notAllChecked;
				parent.indeterminate = checked.length > 0 && notAllChecked;
			}
		}
	}
</script>

<div class="checkbox-group-container">
	<div class="checkbox-group">
		<CheckboxSingle name={group} value={group} onclick={checkForSelected} data-parent />
		{#each data as item}
			<CheckboxSingle name={group} value={item} onclick={checkForSelected} data-child />
		{/each}
	</div>
</div>

<style>
	* {
		border: 0;
		box-sizing: border-box;
		margin: 0;
		padding: 0;
	}
	:root {
		--hue: 223;
		--bg: hsl(var(--hue), 10%, 90%);
		--fg1: hsl(var(--hue), 10%, 10%);
		--fg2: hsl(var(--hue), 10%, 30%);
		--fg3: hsl(var(--hue), 10%, 70%);
		--primary: hsl(var(--hue), 90%, 55%);
		--primary-t: hsla(var(--hue), 90%, 55%, 0);
		--primary-t-hover: hsla(var(--hue), 90%, 55%, 0.15);
		--trans-dur1: 0.3s;
		--trans-dur2: 0.6s;
		font-size: calc(16px + (24 - 16) * (100vw - 320px) / (1280 - 320));
	}
	body,
	input {
		font:
			1em/1.5 'DM Sans',
			sans-serif;
	}
	body {
		background-color: var(--bg);
		color: var(--fg2);
		height: 100vh;
		display: grid;
		place-items: center;
		transition:
			background-color var(--trans-dur1),
			color var(--trans-dur1);
	}
	.checkbox-group {
		margin-bottom: 2em;
	}

	/* .checkbox-group :not(:first-child) {
		margin-left: 2em;
	} */
	/* .checkbox-label:first-of-type:has(input[data-top]) ~ .checkbox-text {
	 margin-left: 2em !important;
	} */
	/* .checkbox-group:first-child:has(input:not([data-top])) {
		margin-left: 0em !important;
	} */
	/* form {
		min-width: 16em;
		padding: 1.5em 1.5em 0 1.5em;
	} */
</style>
