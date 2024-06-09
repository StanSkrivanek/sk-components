<script lang="ts">
	import { onMount } from 'svelte';
	import CheckboxSingle from './CheckboxSingle.svelte';
const desktop = ['Mac Studio', 'Mac Mini', 'iMac', 'Mac Pro'];
	interface Props {
		data: string[];
	}

	const { data }: Props = $props();

	onMount(() => {
		const checklist = new Checklist('.checkbox-group-container');
		console.log(checklist);
	});

	class Checklist {
		[x: string]: any;
		constructor(qs: string) {
			this.el = document.querySelector(qs);
			this.el?.addEventListener('change', this.checkForSelected.bind(this));
			this.init();
		}

		init() {
			const inputs = this.el.querySelectorAll('input');
			console.log('inputs', inputs);

			Array.from(inputs).forEach((el: any) => {
				el.checked = false;
			});
		}
		checkForSelected(e: any) {
			const tar = e.target;
			const isTop = tar.hasAttribute('data-top');
			// console.log(isTop);

			this.updateChecks(tar.name, isTop);
		}

		updateChecks(name: string, isTop = false) {
			if (name) {
				const topCheck = this.el.querySelector(`[name="${name}"][data-top]`);
				const checkItems = this.el.querySelectorAll(`[name="${name}"]:not([data-top])`);
				const checked = Array.from(checkItems).filter((el: any) => el.checked);
				const notAllChecked = checked.length < checkItems.length;

				if (isTop) {
					Array.from(checkItems).forEach((el: any) => {
						el.checked = notAllChecked;
					});
				} else {
					topCheck.checked = !notAllChecked;
					topCheck.indeterminate = checked.length > 0 && notAllChecked;
				}
			}
		}
	}
</script>

<div class="checkbox-group-container">
	<div class="checkbox-group">
		<CheckboxSingle name="desktop" value="Apple Desktop" data-top />
		{#each data as item}
			<CheckboxSingle name="desktop" value={item} data-child />
		{/each}
	</div>
	<!-- <div class="checkbox-group">
		<CheckboxSingle name="mobile" value="Apple Mobile" data-top />
		{#each data as device}
			<CheckboxSingle name="mobile" value={device} data-child />
		{/each}
	</div> -->
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
