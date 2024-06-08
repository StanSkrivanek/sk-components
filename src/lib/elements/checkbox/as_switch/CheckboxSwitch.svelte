<script lang="ts">
	// temporary ID for the switch input element to be able to tab to it with the keyboard. In real application the Id should be generated standars ways.
	const thisId = Math.random().toString(36).substring(2, 15);
	//  OR
	// const itsId = crypto.getRandomValues(new Uint32Array(1))[0].toString(36);

	interface Props {
		is?: string;
		disabled?: boolean;
		hasLabel?: boolean;
	}

	let { is, disabled, hasLabel }: Props = $props();

	let isOn = $state(false);

	function handleToggle() {
		isOn = !isOn;
		console.log(isOn);
	}
</script>

<label for={thisId} class={`gui-switch ${is}`}>
	<span aria-hidden="true" class="sr-only">{isOn ? 'On' : 'Off'}</span>
	<input
		class={is}
		type="checkbox"
		role="switch"
		aria-checked={isOn}
		onclick={handleToggle}
		onkeyup={() => handleToggle}
		id={thisId}
		tabindex="0"
		{disabled}
	/>
	{#if hasLabel}
		<span aria-hidden="true" class:off={disabled === true}>{isOn ? 'On' : 'Off'}</span>
	{/if}
</label>

<style>
	.gui-switch {
		--_private-color: var(--item-color, var(--hsl-lightgray));

		--radius: 0.25rem;

		--thumb-size: 1.6rem;
		--thumb: hsl(var(--hsl-white));
		--thumb-highlight: hsl(var(--_private-color) / 0.5);
		--thumb-color: var(--thumb);

		--track-size: calc(var(--thumb-size) * 2.1);
		--track-padding: 2px;
		--track-inactive: hsl(var(--hsl-lightgray));
		--track-active: hsl(var(--item-color, var(--hsl-green)));

		--track-color-inactive: var(--track-inactive);
		--track-color-active: var(--track-active);

		display: flex;
		align-items: center;
		gap: 0.5rem;
		justify-content: flex-start;

		user-select: none;
		transition: all 0.26s ease-in-out;
		-webkit-tap-highlight-color: transparent;

		& > span {
			width: 3ch;
			text-transform: uppercase;
		}
		& .off {
			color: hsl(var(--hsl-platinum));
		}
		& > input {
			--thumb-position: 0%;
			--thumb-transition-duration: 0.25s;

			/* hide original checkbox */
			appearance: none;

			display: grid;
			align-items: center;
			grid: [track] 1fr / [track] 1fr;

			box-sizing: content-box;
			padding: var(--track-padding);
			background: var(--track-inactive);
			inline-size: var(--track-size);
			block-size: var(--thumb-size);
			border-radius: var(--radius);
			outline-offset: 3px;

			cursor: pointer;
			touch-action: pan-y;

			transition: background-color 0.26s ease-in-out;

			&:focus,
			&:hover {
				outline: 2px solid var(--track-active);
			}

			&::before {
				content: '';
				grid-area: track;
				inline-size: var(--thumb-size);
				block-size: var(--thumb-size);
				background: var(--thumb-color);

				border-radius: var(--radius);
				transform: translateX(var(--thumb-position));
				transition: all 0.26s ease-in-out;

				@media (--motionOK) {
					& {
						transition:
							transform var(--thumb-transition-duration) ease,
							box-shadow 0.26s ease;
					}
				}
			}

			&:checked {
				background: var(--track-active);
				--thumb-position: calc((var(--track-size) - 100%));
			}

			&:indeterminate {
				--thumb-position: calc(calc(calc(var(--track-size) / 2) - calc(var(--thumb-size) / 2)));
			}

			&:disabled {
				cursor: not-allowed;
				outline-color: transparent;
				opacity: 0.5;

				&::before {
					cursor: not-allowed;

					@media (prefers-color-scheme: dark) {
						& {
							box-shadow: inset 0 0 0 2px hsl(0 0% 0% / 50%);
						}
					}
				}
			}
		}
	}
	/* hide  */
	.sr-only {
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

	.pill, .pill:before{
		border-radius: 10rem !important;
	}
</style>
