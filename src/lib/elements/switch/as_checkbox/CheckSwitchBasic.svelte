<script lang="ts">
	// import type { Snippet } from 'svelte';
	// export const { is, children } = $props();
</script>

<label for="switch" class="gui-switch">
	Label text
	<input type="checkbox" role="switch" id="switch" />
</label>

<style>
	.gui-switch {
		--thumb-size: 2rem;
		--thumb: hsl(0 0% 100%);
		--thumb-highlight: hsl(0 0% 0% / 25%);

		--track-size: calc(var(--thumb-size) * 2);
		--track-padding: 2px;
		--track-inactive: hsl(80 0% 80%);
		--track-active: hsl(80 60% 45%);
			/* --border-width: calc(var(--general-size) / 10); */
		/* --_private-color: var(--item-color, var(--hsl-lightgray)); */

		--thumb-color: var(--thumb);
		--thumb-color-highlight: var(--thumb-highlight);
		--track-color-inactive: var(--track-inactive);
		--track-color-active: var(--track-active);

		--isLTR: 1;

		display: flex;
		align-items: center;
		gap: 2ch;
		justify-content: space-between;

		cursor: pointer;
		user-select: none;
		transition: all 0.26s ease-in-out;
		-webkit-tap-highlight-color: transparent;

		/* @media (prefers-color-scheme: dark) {
			& {
				--thumb: hsl(0 0% 5%);
				--thumb-highlight: hsl(0 0% 100% / 25%);
				--track-inactive: hsl(80 0% 35%);
				--track-active: hsl(80 60% 60%);
			}
		} */

		&:dir(rtl) {
			--isLTR: -1;
		}

		& > input {
			--thumb-position: 0%;
			--thumb-transition-duration: 0.25s;

			padding: var(--track-padding);
			background: var(--track-color-inactive);
			inline-size: var(--track-size);
			block-size: var(--thumb-size);
			border-radius: var(--track-size);

			appearance: none;
			pointer-events: none;
			touch-action: pan-y;
			border: none;
			outline-offset: 5px;
			box-sizing: content-box;

			flex-shrink: 0;
			display: grid;
			align-items: center;
			grid: [track] 1fr / [track] 1fr;
			transition: background-color 0.26s ease-in-out;

			&::before {
				--highlight-size: 0;

				content: '';
				cursor: pointer;
				pointer-events: auto;
				grid-area: track;
				inline-size: var(--thumb-size);
				block-size: var(--thumb-size);
				background: var(--thumb-color);
				box-shadow: 0 0 0 var(--highlight-size) var(--thumb-color-highlight);
				border-radius: 50%;
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

			&:not(:disabled):hover::before {
				--highlight-size: 0.5rem;
			}

			&:checked {
				background: var(--track-color-active);
				--thumb-position: calc((var(--track-size) - 100%) * var(--isLTR));
			}

			&:indeterminate {
				--thumb-position: calc(
					calc(calc(var(--track-size) / 2) - calc(var(--thumb-size) / 2)) * var(--isLTR)
				);
			}

			&:disabled {
				cursor: not-allowed;
				--thumb-color: transparent;

				&::before {
					cursor: not-allowed;
					box-shadow: inset 0 0 0 2px hsl(0 0% 100% / 50%);

					@media (prefers-color-scheme: dark) {
						& {
							box-shadow: inset 0 0 0 2px hsl(0 0% 0% / 50%);
						}
					}
				}
			}
		}
	}
</style>
