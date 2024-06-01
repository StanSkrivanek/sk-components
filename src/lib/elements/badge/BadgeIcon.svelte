<script lang="ts">
	import type { Snippet } from 'svelte';
	export const { is, children } = $props();
</script>

<span class={is}
	>{@render (children as Snippet)()}
	<span class="icon">
		<svg width="24" height="24" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
			<path
				d="M22.7071 1.29289C23.0976 1.68342 23.0976 2.31658 22.7071 2.70711L2.70711 22.7071C2.31658 23.0976 1.68342 23.0976 1.29289 22.7071C0.902369 22.3166 0.902369 21.6834 1.29289 21.2929L21.2929 1.29289C21.6834 0.902369 22.3166 0.902369 22.7071 1.29289Z"
			></path>
			<path
				d="M1.29289 1.29289C1.68342 0.902369 2.31658 0.902369 2.70711 1.29289L22.7071 21.2929C23.0976 21.6834 23.0976 22.3166 22.7071 22.7071C22.3166 23.0976 21.6834 23.0976 21.2929 22.7071L1.29289 2.70711C0.902369 2.31658 0.902369 1.68342 1.29289 1.29289Z"
			></path>
		</svg></span
	>
</span>

<style>
	span {
		--_private-color: var(--item-color, var(--hsl-steel));
		color: color-mix(in oklab, hsl(var(--_private-color)), white 80%);
		background: color-mix(in oklab, hsl(var(--_private-color)), white 3%);
		display: inline-flex;
		width: max-content;
		padding: 0.25rem 0.5rem;
		border-radius: 0.1rem;
		font-size: var(--xs);
		letter-spacing: 0.02rem;
		text-transform: uppercase;
		font-family: var(--fw-bold);
		&.icon {
			cursor: pointer;
			padding: 0;
			background: none;
			svg {
				width: 10px;
				height: 10px;
				fill: color-mix(in oklab, hsl(var(--_private-color)), white 60%);
				stroke: color-mix(in oklab, hsl(var(--_private-color)), white 60%);
			}
		}
		&:has(svg) {
			display: flex;
			align-items: center;
			justify-content: space-between;
			gap: 1rem;
			svg {
				width: 10px;
				height: 10px;
				fill: color-mix(in oklab, hsl(var(--_private-color)), white 60%);
			}
		}

		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--_private-color)), white 30%);
			color: color-mix(in oklab, hsl(var(--_private-color)), black 10%);
			padding-inline: 0.5rem !important;
			background: transparent;
		}

		&.medium {
			font-size: var(--sm);
			letter-spacing: -0.02rem;
			/* padding: 0.25rem 1rem; */
		}

		&.pill {
			border-radius: 100px;
			padding-inline: 0.75rem;
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
