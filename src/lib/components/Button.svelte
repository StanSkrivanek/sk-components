<script lang="ts">
	import type { Snippet } from 'svelte';
	export const { is, children } = $props();
</script>

<button class={is}>{@render (children as Snippet)()}</button>

<style>
	button {
		--_private-color: var(--item-color, var(--hsl-primary));
		cursor: pointer;
		display: inline-block;
		color: color-mix(in oklab, hsl(var(--_private-color)), white 80%);
		background: color-mix(in oklab, hsl(var(--_private-color)), white 3%);
		padding: 1rem 2.2rem;
		border: none;
		border-radius: 0.25rem;
		font-size: var(--sm);
		letter-spacing: 0.02rem;
		text-transform: uppercase;
		font-family: var(--fw-bold);
		transition: all 0.1s ease-in-out;
		&:hover {
			background: color-mix(in oklab, hsl(var(--_private-color)), black 10%);
			color: color-mix(in oklab, hsl(var(--_private-color)), white 90%);
		}
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--_private-color)), white 30%);
			color: color-mix(in oklab, hsl(var(--_private-color)), black 10%);
			background: transparent;
			&:hover {
				background: color-mix(in oklab, hsl(var(--_private-color)), white 80%);
				color: color-mix(in oklab, hsl(var(--_private-color)), black 30%);
			}
		}
		&.large {
			font-size: var(--md);
			letter-spacing: -0.02rem;
			padding: 1.2rem 3rem;
		}
		&.medium {
			font-size: var(--sm);
			letter-spacing: -0.02rem;
			padding: 0.75rem 1.6rem;
		}
		&.small {
			padding: 0.75rem 1.4rem;
			font-size: var(--xs);
		}
		&.pill {
			border-radius: 100px;
		}
	}

	/* Colors */
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
