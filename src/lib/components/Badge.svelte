<script lang="ts">
	import type { Snippet } from 'svelte';
	export const { is, children } = $props();
</script>

<span class="{is}">{@render (children as Snippet)()}</span>

<style>
	span {
		color: color-mix(in oklab, hsl(var(--hsl-black-matte)), white 80%);
		background: color-mix(in oklab, hsl(var(--hsl-black-matte)), white 10%);
		padding: 0.25rem 0.75rem;
		border-radius: 0.1rem;
		font-size: var(--xs);
		letter-spacing: 0.02rem;
      text-transform: uppercase;
      font-family: var(--fw-bold);
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-black-matte)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-black-matte)), black 10%);
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
	.blue {
		color: color-mix(in oklab, hsl(var(--hsl-blue)), black 30%);
		background: color-mix(in oklab, hsl(var(--hsl-blue)), white 60%);
	}

	.red {
		color: color-mix(in oklab, hsl(var(--hsl-red)), black 30%);
		background: color-mix(in oklab, hsl(var(--hsl-red)), white 60%);
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-red)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-red)), black 10%);
			background: transparent;
		}
	}
	.green {
		color: color-mix(in oklab, hsl(var(--hsl-green)), black 30%);
		background: color-mix(in oklab, hsl(var(--hsl-green)), white 60%);
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-green)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-green)), black 10%);
			background: transparent;
		}
	}
	.yellow {
		color: color-mix(in oklab, hsl(var(--hsl-gold)), black 30%);
		background: color-mix(in oklab, hsl(var(--hsl-gold)), white 60%);
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-gold)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-gold)), black 10%);
			background: transparent;
		}
	}
	
	.purple {
		color: color-mix(in oklab, hsl(var(--hsl-purple)), black 30%);
		background: color-mix(in oklab, hsl(var(--hsl-purple)), white 60%);
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-purple)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-purple)), black 10%);
			background: transparent;
		}
	}
	.pink {
		color: color-mix(in oklab, hsl(var(--hsl-pink)), black 30%);
		background: color-mix(in oklab, hsl(var(--hsl-pink)), white 60%);
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-pink)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-pink)), black 10%);
			background: transparent;
		}
	}
	.disabled {
		color: color-mix(in oklab, hsl(var(--hsl-platinum)), black 10%);
		background: color-mix(in oklab, hsl(var(--hsl-platinum)), white 60%);
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-platinum)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-platinum)), black 10%);
			background: transparent;
		}
	}
	.cyan {
		color: color-mix(in oklab, hsl(var(--hsl-cyan)), black 30%);
		background: color-mix(in oklab, hsl(var(--hsl-cyan)), white 60%);
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-cyan)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-cyan)), black 10%);
			background: transparent;
		}
	}
	.orange {
		color: color-mix(in oklab, hsl(var(--hsl-orange)), black 30%);
		background: color-mix(in oklab, hsl(var(--hsl-orange)), white 60%);
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-orange)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-orange)), black 10%);
			background: transparent;
		}
	}
	.steel {
		color: color-mix(in oklab, hsl(var(--hsl-steel)), black 30%);
		background: color-mix(in oklab, hsl(var(--hsl-steel)), white 60%);
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-steel)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-steel)), black 10%);
			background: transparent;
		}
	}
	.black {
		color: color-mix(in oklab, hsl(var(--hsl-black-matte)), white 80%);
		background: color-mix(in oklab, hsl(var(--hsl-black-matte)), white 10%);
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-black-matte)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-black-matte)), black 10%);
			background: transparent;
		}
	}
</style>
