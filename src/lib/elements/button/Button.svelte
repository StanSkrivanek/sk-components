<script lang="ts">
	import type { Snippet } from 'svelte';
	export const { is, children, onClick } = $props();
</script>

<button class={is} tabindex="0" onclick={() => onClick()} onkeyup={() => onClick()}
	>{@render (children as Snippet)()}</button
>
<style>
	button {
		/* private color contains --item-color that is passed in from props and fallback - the main color */
		/* current fallback is se to neutral color but i can be set eg. to --hsl-primary that is passed from app.css*/
		/* --_private-color: var(--item-color, var(--hsl-primary)); */

		--_private-color: var(--item-color, var(--hsl-steel));
		cursor: pointer;
		color: color-mix(in oklab, hsl(var(--_private-color)), white 80%);
		background: color-mix(in oklab, hsl(var(--_private-color)), white 3%);
		padding: 0.75rem 2.2rem;
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

		&.lg {
			font-size: var(--md);
			letter-spacing: -0.02rem;
			padding: 1.2rem 3.2rem;
		}
		&.md {
			font-size: var(--sm);
			letter-spacing: -0.02rem;
			padding: 1rem 2rem;
		}
		&.sm {
			padding: 0.75rem 1.4rem;
			font-size: var(--xs);
		}
		&.xs {
			padding: 0.5rem 1rem;
			font-size: var(--xxs);
		}
		&.rounded {
			border-radius: 0.5rem;
		}

		&.pill {
			border-radius: 100px;
		}
		&.block {
			display: block;
			width: 100%;
		}
	}

	/* Colors - can be used in Global app.css instead of here*/
	.primary {
		--item-color: var(--hsl-primary);
	}

	.secondary {
		--item-color: var(--hsl-secondary);
	}
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
