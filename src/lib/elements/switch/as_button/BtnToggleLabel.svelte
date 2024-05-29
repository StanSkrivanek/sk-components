<script lang="ts">
	// NOTE: Switches: A switch is a control that toggles a single setting on or off, much like a light switch. It's used for binary options where the user must choose between two states, such as enabling/disabling settings. Switches are ideal for real-time settings that take effect immediately.
	type Props = {
		is?: string | null;
	};

	let { is }: Props = $props();

	let isOn = $state(false);

	function handleToggle() {
		isOn = !isOn;
	}
</script>

<div class="switch__w">
	<button
		class={`${is} `}
		type="button"
		aria-checked={isOn}
		onclick={handleToggle}
		onkeyup={() => handleToggle}
		role="switch"
	>
		<span aria-hidden="true" class="sr-only">off</span>
		<span aria-hidden="true" class="sr-only">on</span>
		<span aria-hidden="true" class="toggle-inner"></span>
	</button>
	<!-- if isOn labe is `On` and if !isOn label is `Off`  -->
	<span>
		{isOn ? 'On' : 'Off'}
	</span>
</div>

<style>
	.switch__w {
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
		--general-size: 30px;
		--border-width: calc(var(--general-size) / 10);
		--_private-color: var(--item-color, var(--hsl-lightgray));
		--checked-color: var(--item-color, var(--hsl-green));

		position: relative;
		display: inline-flex;
		align-items: center;
		cursor: pointer;
		border: var(--border-width) solid color-mix(in oklab, hsl(var(--hsl-lightgray)), white 5%);
		border-radius: 100px;
		height: var(--general-size);
		width: calc(var(--general-size) * 2);
		background: color-mix(in oklab, hsl(var(--hsl-lightgray)), white 5%);
		transition: all 0.1s ease-in-out;

		&:focus,
		&:hover {
			outline: 2px solid hsl(var(--checked-color));
			outline-offset: 3px;
		}
		&[aria-checked='true'] {
			/* --checked-color: var(--item-color, var(--hsl-green)); */
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
