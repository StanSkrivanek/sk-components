<script lang="ts">
	// import type { Snippet } from 'svelte';

	interface Props {
		is: string;
	}
	
	let { is }: Props = $props();

	let isOn = $state(false);

	function handleToggle() {
		isOn = !isOn;
	}
</script>

<button
	class={`${is} toggle ${isOn ? 'isOn' : 'isOff'}`}
	type="button"
	aria-checked={isOn}
	onclick={handleToggle}
	onkeyup={handleToggle}
	role="switch"
>
	<span aria-hidden="true" class="sr-only">off</span>
	<span aria-hidden="true" class="sr-only">on</span>
	<span aria-hidden="true" class="toggle-inner"></span>
</button>

<style>
	button[role='switch'] {
		--general-size: 30px;
		--border-width: calc(var(--general-size) / 10);
		--_private-color: var(--item-color, var(--hsl-lightgray));

		position: relative;
		display: inline-flex;
		align-items: center;
		cursor: pointer;
		border: var(--border-width) solid color-mix(in oklab, hsl(var(--hsl-lightgray)), white 5%);
		border-radius: 100px;
		transition: all 0.2s ease-in-out;
		height: var(--general-size);
		width: calc(var(--general-size) * 2);
		background: color-mix(in oklab, hsl(var(--hsl-lightgray)), white 5%);

		&[aria-checked='true'] {
			--checked-color: var(--item-color, var(--hsl-green));
			background: hsl(var(--checked-color));
			border-color: hsl(var(--checked-color));
			& .toggle-inner {
				transform: translateX(var(--general-size));
			}
			& .toggle-inner {
				border-color: hsl(var(--checked-color));
			}
		}

		& .toggle-inner {
			position: absolute;
			top: calc(var(--border-width) * -1);
			left: calc(var(--border-width) * -1);
			width: var(--general-size);
			height: var(--general-size);
			border-radius: 100px;
			background: white;
			border: var(--border-width) solid color-mix(in oklab, hsl(var(--hsl-lightgray)), white 5%);
			transition: all 0.2s ease-in-out;
		}

		& .sr-only {
			position: absolute;
			height: 1px;
			width: 1px;
			padding: 0;
			margin: -1px;
			clip: rect(0, 0, 0, 0);
			clip-path: inset(0%);
			overflow: hidden;
			font-size: var(--xs);
			white-space: nowrap;
		}
	}

	/* Colors - can be used in Global app.css instead of here*/
	.red {
		--item-color: var(--hsl-red);
	}

	.orange {
		--item-color: var(--hsl-orange);
	}

	.yellow {
		--item-color: var(--hsl-gold);
	}

	.green {
		--item-color: var(--hsl-green);
	}
	.blue {
		--item-color: var(--hsl-blue);
	}

	.purple {
		--item-color: var(--hsl-purple);
	}

	.cyan {
		--item-color: var(--hsl-cyan);
	}

	.pink {
		--item-color: var(--hsl-pink);
	}

	.platinum {
		--item-color: var(--hsl-platinum);
	}

	.steel {
		--item-color: var(--hsl-steel);
	}

	.black {
		--item-color: var(--hsl-black-matte);
	}
</style>
