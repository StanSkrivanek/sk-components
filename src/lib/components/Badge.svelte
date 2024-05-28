<script lang="ts">
	import type { Snippet } from 'svelte';
	export const { is, children } = $props();
</script>

<span class={is}>{@render (children as Snippet)()}</span>

<style>
	span {
		--_private-color: var(--item-color, var(--hsl-primary));
		color: color-mix(in oklab, hsl(var(--_private-color)), white 80%);
		background: color-mix(in oklab, hsl(var(--_private-color)), white 3%);
		padding: 0.25rem 0.75rem;
		border-radius: 0.1rem;
		font-size: var(--xs);
		letter-spacing: 0.02rem;
		text-transform: uppercase;
		font-family: var(--fw-bold);
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--_private-color)), white 30%);
			color: color-mix(in oklab, hsl(var(--_private-color)), black 10%);
			background: transparent;
		}
		&.medium {
			font-size: var(--sm);
			letter-spacing: -0.02rem;
			padding: 0.25rem 1rem;
		}
		&.pill {
			border-radius: 100px;
			padding-inline: 1rem;
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
