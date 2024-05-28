<script lang="ts">
	import type { Snippet } from 'svelte';
	export const { is, children } = $props();
</script>

<button class={is}>{@render (children as Snippet)()}</button>

<style>
	button {
		cursor: pointer;
		display: inline-block;
		color: color-mix(in oklab, hsl(var(--hsl-black-matte)), white 80%);
		background: color-mix(in oklab, hsl(var(--hsl-black-matte)), white 10%);
		padding: 1rem 2.2rem;
		border: none;
		border-radius: 0.25rem;
		font-size: var(--sm);
		letter-spacing: 0.02rem;
		text-transform: uppercase;
		font-family: var(--fw-bold);
		transition: all 0.1s ease-in-out;
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-black-matte)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-black-matte)), black 10%);
			background: transparent;
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
			/* padding-inline: 1rem; */
		}
	}

	.blue {
		color: color-mix(in oklab, hsl(var(--hsl-blue)), black 30%);
		background: color-mix(in oklab, hsl(var(--hsl-blue)), white 60%);
		&:hover {
			background: color-mix(in oklab, hsl(var(--hsl-blue)), black 5%);
			color: color-mix(in oklab, hsl(var(--hsl-blue)), white 80%);
		}
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-blue)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-blue)), black 10%);
			background: transparent;
			&:hover {
				background: color-mix(in oklab, hsl(var(--hsl-blue)), white 80%);
			}
		}
	}

	.red {
		color: color-mix(in oklab, hsl(var(--hsl-red)), black 30%);
		background: color-mix(in oklab, hsl(var(--hsl-red)), white 60%);
		&:hover {
			background: color-mix(in oklab, hsl(var(--hsl-red)), black 5%);
			color: color-mix(in oklab, hsl(var(--hsl-red)), white 80%);
		}
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-red)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-red)), black 10%);
			background: transparent;
			&:hover {
				background: color-mix(in oklab, hsl(var(--hsl-red)), white 80%);
			}
		}
	}
	.green {
		color: color-mix(in oklab, hsl(var(--hsl-green)), black 30%);
		background: color-mix(in oklab, hsl(var(--hsl-green)), white 60%);
		&:hover {
			background: color-mix(in oklab, hsl(var(--hsl-green)), black 5%);
			color: color-mix(in oklab, hsl(var(--hsl-green)), white 80%);
		}
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-green)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-green)), black 10%);
			background: transparent;
			&:hover {
				background: color-mix(in oklab, hsl(var(--hsl-green)), white 80%);
			}
		}
	}

	.yellow {
		color: color-mix(in oklab, hsl(var(--hsl-gold)), black 30%);
		background: color-mix(in oklab, hsl(var(--hsl-gold)), white 60%);
		&:hover {
			background: color-mix(in oklab, hsl(var(--hsl-gold)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-gold)), black 33%);
		}
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-gold)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-gold)), black 10%);
			background: transparent;
			&:hover {
				background: color-mix(in oklab, hsl(var(--hsl-gold)), white 80%);
				color: color-mix(in oklab, hsl(var(--hsl-gold)), black 30%);
			}
		}
	}

	.purple {
		color: color-mix(in oklab, hsl(var(--hsl-purple)), black 30%);
		background: color-mix(in oklab, hsl(var(--hsl-purple)), white 60%);
		&:hover {
			background: color-mix(in oklab, hsl(var(--hsl-purple)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-purple)), white 90%);
		}
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-purple)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-purple)), black 10%);
			background: transparent;
			&:hover {
				background: color-mix(in oklab, hsl(var(--hsl-purple)), white 80%);
				color: color-mix(in oklab, hsl(var(--hsl-purple)), black 30%);
			}
		}
	}

	.pink {
		color: color-mix(in oklab, hsl(var(--hsl-pink)), black 30%);
		background: color-mix(in oklab, hsl(var(--hsl-pink)), white 60%);
		&:hover {
			background: color-mix(in oklab, hsl(var(--hsl-pink)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-pink)), white 90%);
		}
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-pink)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-pink)), black 10%);
			background: transparent;
			&:hover {
				background: color-mix(in oklab, hsl(var(--hsl-pink)), white 80%);
				color: color-mix(in oklab, hsl(var(--hsl-pink)), black 30%);
			}
		}
	}
	.platinum {
		/* pointer-events: none; */
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
		&:hover {
			background: color-mix(in oklab, hsl(var(--hsl-cyan)), white 30%);
			/* color: color-mix(in oklab, hsl(var(--hsl-cyan)), white 90%); */
		}
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-cyan)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-cyan)), black 10%);
			background: transparent;
			&:hover {
				background: color-mix(in oklab, hsl(var(--hsl-cyan)), white 80%);
				color: color-mix(in oklab, hsl(var(--hsl-cyan)), black 30%);
			}
		}
	}
	.orange {
		color: color-mix(in oklab, hsl(var(--hsl-orange)), black 30%);
		background: color-mix(in oklab, hsl(var(--hsl-orange)), white 60%);
		&:hover {
			background: color-mix(in oklab, hsl(var(--hsl-orange)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-orange)), white 90%);
		}
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-orange)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-orange)), black 10%);
			background: transparent;
			&:hover {
				background: color-mix(in oklab, hsl(var(--hsl-orange)), white 80%);
				color: color-mix(in oklab, hsl(var(--hsl-orange)), black 30%);
			}
		}
	}
	.steel {
		color: color-mix(in oklab, hsl(var(--hsl-steel)), black 30%);
		background: color-mix(in oklab, hsl(var(--hsl-steel)), white 60%);
		&:hover {
			background: color-mix(in oklab, hsl(var(--hsl-steel)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-steel)), white 90%);
		}
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-steel)), white 30%);
			color: color-mix(in oklab, hsl(var(--hsl-steel)), black 10%);
			background: transparent;
			&:hover {
				background: color-mix(in oklab, hsl(var(--hsl-steel)), white 80%);
				color: color-mix(in oklab, hsl(var(--hsl-steel)), black 30%);
			}
		}
	}

	.black {
		color: color-mix(in oklab, hsl(var(--hsl-black-matte)), white 80%);
		background: color-mix(in oklab, hsl(var(--hsl-black-matte)), white 10%);
		&:hover {
			background: color-mix(in oklab, hsl(var(--hsl-black-matte)), white 25%);
			color: color-mix(in oklab, hsl(var(--hsl-black-matte)), white 100%);
		}
		&.outline {
			border: 1px solid color-mix(in oklab, hsl(var(--hsl-black-matte)), white 40%);
			color: color-mix(in oklab, hsl(var(--hsl-black-matte)), white 20%);
			background: transparent;
			&:hover {
				background: color-mix(in oklab, hsl(var(--hsl-black-matte)), white 90%);
				color: color-mix(in oklab, hsl(var(--hsl-black-matte)), white 10%);
			}
		}
	}
</style>
