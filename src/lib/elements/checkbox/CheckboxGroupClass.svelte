<script lang="ts">
	// @ts-nocheck

	import CheckboxSingle from './CheckboxSingle.svelte';
	// const desktop = ['Mac Studio', 'Mac Mini', 'iMac', 'Mac Pro'];
	interface Props {
		data: string[];
		group: string;
	}

	const { data, group }: Props = $props();
	// let inputs = [];
	// let children = [];
	$effect(() => {
		const checkboxCroups = [...document.querySelectorAll('.checkbox-group')];
		// console.log("🚀 ~ onMount ~ checkboxCroups:", checkboxCroups)
		checkboxCroups.forEach((group: any) => {
			const inputs = [...group.querySelectorAll('input')];
			// console.log("🚀 ~ checkboxCroups.forEach ~ inputs:", inputs)
			inputs.forEach((el: any) => {
				(el as HTMLInputElement).checked = false;
				// console.log(el.checked);
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
			// }
		}
	}
</script>

<div class="checkbox-group-container">
	<div class="checkbox-group">
		<CheckboxSingle name={group} value={group} data-parent onclick={checkForSelected} />
		{#each data as item}
			<CheckboxSingle name={group} value={item} data-child onclick={checkForSelected} />
			<!-- <label class="checkbox-label">
				<input class="checkbox" type="checkbox" name={group} value={item} data-child/>
				<svg class="check-icon" width="24px" height="24px" viewBox="0 0 24 24">
					<g fill="none" stroke-linecap="round" stroke-linejoin="round" stroke-width="2">
						<rect class="check-icon__box" x="1" y="1" width="22" height="22" />
						<polyline
							class="check-icon__box-worm"
							points="23,1 1,1 1,23 23,23 23,4"
							stroke-dasharray="30 146"
							stroke-dashoffset="30"
						/>
						<polyline
							class="check-icon__check-worm"
							points="23,4 10,17 5,12 18,12"
							stroke-dasharray="17.38 149.68"
							stroke-dashoffset="103.38"
						/>
					</g>
				</svg>
				<span class="checkbox-text">{item}</span>
			</label> -->
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
