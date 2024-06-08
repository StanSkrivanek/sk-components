<script lang="ts">
	import type { Snippet } from 'svelte';

	// temporary ID for the switch input element to be able to tab to it with the keyboard. In real application the Id should be generated standars ways.
	const thisId = Math.random().toString(36).substring(2, 15);
	//  OR
	// const itsId = crypto.getRandomValues(new Uint32Array(1))[0].toString(36);

	interface Props {
		name?: string;
		is?: string;
		label?: string;
		checked?: true;
		showState?: boolean;
		disabled?: boolean;
		children?: Snippet;
		role?: string;
		isParent?: boolean;
	}

	let { is, name, disabled, checked, label, showState, role, isParent, children }: Props = $props();
</script>

<label class={`gui-switch`}>
	<span aria-hidden="true" class="sr-only">{checked ? 'On' : 'Off'}</span>
	<input
		type="checkbox"
		value={checked ? 'On' : 'Off'}
		id={thisId}
		class={is}
		tabindex="0"
		data-parent={isParent}
		aria-checked={checked}
		{name}
		{role}
		{disabled}
		{checked}
	/>
	<!-- display state Yes/No | On/Off in the label -->
	{#if showState}
		<span aria-hidden="true" class:off={disabled === true}>{checked ? 'On' : 'Off'}</span>
	{/if}
	{#if label}
		<span aria-hidden="true" class:off={disabled === true}>{label}</span>
	{/if}
	<!-- display children between starting and ending tags ONLY if prop label is not defined. Prop labe takes precedence -->
	{#if !label && children}
		{@render children()}
	{/if}
</label>

<style>
	.gui-switch {
		--_private-color: var(--item-color, var(--hsl-white));

		--radius: 0.25rem;

		--checkbox-size: 0.75rem;
		/* --checkbox: hsl(var(--hsl-white)); */
		--checkbox-highlight: hsl(var(--_private-color) / 0.5);
		--checkbox-color: hsl(var(--hsl-transparent));

		--track-size: var(--checkbox-size);
		--track-padding: 2px;
		--track-inactive: hsl(var(--hsl-white));
		--track-active: hsl(var(--item-color, var(--hsl-green)));

		user-select: none;
		display: flex;
		align-items: center;
		gap: 0.5rem;
		justify-content: flex-start;
		margin-bottom: 0.5rem;
		/* transition: all 0.26s ease-in-out; */
		-webkit-tap-highlight-color: transparent;

		& > span {
			min-width: 4ch;
			/* text-transform: uppercase; */
		}
		& .off {
			color: hsl(var(--hsl-platinum));
		}
		& > input {
			--checkbox-position: 0%;
			--checkbox-transition-duration: 0.25s;

			/* hide original checkbox */
			appearance: none;
			position: relative;
			display: grid;
			align-items: center;
			grid: [track] 1fr / [track] 1fr;

			box-sizing: content-box;
			padding: var(--track-padding);
			background: var(--track-inactive);
			inline-size: var(--track-size);
			block-size: var(--checkbox-size);

			border: 1px solid hsl(var(--hsl-gray));
			border-radius: var(--radius);
			outline-offset: 3px;

			cursor: pointer;

			transition: background-color 0.26s ease-in-out;

			/* set group of checkboxes under parent checkbox to right as in eg. a list */
			&:not([data-parent='true']) {
				margin-left: calc(var(--checkbox-size) * 1.5);
			}
			&:focus,
			&:hover {
				outline: 2px solid var(--track-active);
			}

			&::before {
				content: '';
				position: absolute;
				top: calc(var(--checkbox-size) * 0.046);
				left: calc(var(--checkbox-size) * 0.25);
				grid-area: track;
				inline-size: calc(var(--checkbox-size) * 0.5);
				block-size: calc(var(--checkbox-size) * 0.75);
				rotate: 43deg;
				border: calc(var(--checkbox-size) * 0.2) solid transparent;
				border-top: 0;
				border-left: 0;
			}

			&:checked::before {
				border-color: var(--track-active);
			}

			&:disabled {
				cursor: not-allowed;
				outline-color: transparent;
				opacity: 0.5;

				&::before {
					cursor: not-allowed;

					/* @media (prefers-color-scheme: dark) {
						& {
							box-shadow: inset 0 0 0 2px hsl(0 0% 0% / 50%);
						}
					} */
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

	.pill,
	.pill:before {
		border-radius: 10rem !important;
	}
</style>
