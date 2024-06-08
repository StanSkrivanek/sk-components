<script lang="ts">
	type Props = {
		is?: string | null;
		disabled?: boolean;
	};

	let { is, disabled }: Props = $props();

	let isOn = $state(false);

	function handleToggle() {
		isOn = !isOn;
	}
</script>

<div class="gui-switch">
	<button
		type="button"
		role="switch"
		class={is}
		aria-checked={isOn}
		onclick={handleToggle}
		onkeyup={() => handleToggle}
		{disabled}
	>
		<span aria-hidden="true" class="sr-only">{isOn ? 'On' : 'Off'}</span>
		<span aria-hidden="true" class="thumb">
			<span class="thumb-inner">
				{isOn ? 'On' : 'Off'}
			</span>
		</span>
	</button>
</div>

<style>
	.gui-switch {
		display: inline-flex;
		gap: 0.5rem;
		align-items: center;
		justify-content: center;

		& > span {
			font-weight: 600;
			text-transform: uppercase;
			letter-spacing: 0.05rem;
			font-size: var(--xs);
			width: 3ch;
		}
	}
	button[role='switch'] {
		--_private-color: var(--item-color, var(--hsl-lightgray));

		/* Track Width */
		--track-size: calc(var(--thumb-size) * 2);
		/* Thumb border - space between track and thumb */
		--border-size: calc(var(--thumb-size) / 8);
		/* THumb size - determines the height of the thumb and track */
		--thumb-size: 1.8rem;

		/* Track - Active has green color and inactive has gray as default */
		--track-active: var(--item-color, var(--hsl-green));
		--track-inactive: hsl(var(--hsl-lightgray));

		--thumb-color: hsl(var(--hsl-white));
		--thumb-position: 0%;
		

		position: relative;
		display: flex;
		align-items: center;
		padding: 0;
		border: none;
		border-radius: 100px;
		background: var(--track-inactive);
		inline-size: var(--track-size);
		cursor: pointer;
		block-size: var(--thumb-size);
		transition: all 0.1s ease-in-out;

		&:focus,
		&:hover {
			outline: var(--border-size) solid hsl(var(--track-active));
			outline-offset: 2px;
			outline-width: 2px;
		}

		& .thumb {
			display: flex;
			align-items: center;
			justify-content: center;
			width: var(--thumb-size);
			aspect-ratio: 1;
			border-radius: 50%;
			background: var(--thumb-color);
			border: var(--border-size) solid var(--track-inactive);
			transform: translateX(var(--thumb-position));
			transition: all 0.2s ease-in-out;

			& .thumb-inner {
				font-size: calc((var(--thumb-size) - var(--border-size) ) / 2.4); ;
				color: var(--_private-color);
				text-transform: uppercase;
			}
		}

		&[aria-checked='true'] {
			background: hsl(var(--track-active));
			& .thumb {
				transform: translateX(calc(var(--track-size) - var(--thumb-size)));
				border: var(--border-size) solid hsl(var(--track-active));
			}
		}

		&:disabled {
			opacity: 0.5;
			cursor: not-allowed;
			outline: transparent;
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
