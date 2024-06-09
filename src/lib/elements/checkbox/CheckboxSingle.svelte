<script lang="ts">
	interface Props {
		is?: string;
		name?: string;
		value?: string;
		children?: string;
		onClick?: () => void;
		// ...props: any;
		'data-top'?: boolean;
	}

	const { is, name, value, children, onClick, ...props }: Props = $props();
</script>

<label class="checkbox-label">
	<input class="checkbox" type="checkbox" {name} {value} {...props} />
	<svg class="check-icon" width="24px" height="24px" viewBox="0 0 24 24">
		<g fill="none" stroke-linecap="round" stroke-linejoin="round" stroke-width="2">
			<rect class="check-icon__box" x="1" y="1" width="22" height="22" />
			<polyline
				class="check-icon__box-worm"
				points="23,1 1,1 1,23 23,23 23,4"
				stroke-dasharray="30 146"
				stroke-dashoffset="30"
			/>
			<polyline
				class="check-icon__check-worm"
				points="23,4 10,17 5,12 18,12"
				stroke-dasharray="17.38 149.68"
				stroke-dashoffset="103.38"
			/>
		</g>
	</svg>
	<span class="checkbox-text">{value}</span>
</label>

<style>
	.checkbox-label {
		display: flex;
		align-items: center;
		padding: 0.375em;
		position: relative;
		-webkit-user-select: none;
		user-select: none;
		-webkit-tap-highlight-color: transparent;
		& input[data-top] ~ .checkbox-text {
			font-weight: 600;
		}
	}

	/* .checkbox-label + .checkbox-label {
	margin-left: 2em;
} */
	.checkbox-label:not(:first-of-type) {
		margin-left: 2em;
	}
	.checkbox {
		position: absolute;
		clip: rect(1px, 1px, 1px, 1px);
		width: 1px;
		height: 1px;
	}
	.checkbox-text {
		color: var(--fg1);
		transition: color var(--trans-dur1);
	}
	.checkbox-text:after {
		background-color: var(--primary-t);
		border-radius: 0.375em;
		content: '';
		display: block;
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		z-index: -1;
		transition: background-color 0.15s linear;
	}
	.check-icon {
		margin-right: 0.5em;
		width: 1.5em;
		height: 1.5em;
	}
	.check-icon__box {
		stroke: var(--fg3);
		transition: stroke var(--trans-dur1);
	}
	.check-icon__box-worm,
	.check-icon__check-worm {
		stroke: var(--primary);
		transition:
			stroke var(--trans-dur1),
			stroke-dashoffset var(--trans-dur2) cubic-bezier(0.42, -0.2, 0.58, 1.2);
	}

	/* Focus and hover */
	.checkbox:focus ~ .checkbox-text:after,
	.checkbox:hover ~ .checkbox-text:after {
		background-color: var(--primary-t-hover);
	}
	.checkbox:checked + .check-icon .check-icon__box-worm,
	.checkbox:indeterminate + .check-icon .check-icon__box-worm {
		stroke-dashoffset: -91;
	}
	.checkbox:checked + .check-icon .check-icon__check-worm {
		stroke-dashoffset: -6;
	}
	.checkbox:indeterminate + .check-icon .check-icon__box-worm {
		stroke-dashoffset: -111.38;
	}
	.checkbox:indeterminate + .check-icon .check-icon__check-worm {
		stroke-dashoffset: -26.38;
	}

	/* `:focus-visible` support */
	@supports selector(:focus-visible) {
		.checkbox:focus ~ .checkbox-text:after {
			background-color: var(--primary-t);
		}
		.checkbox:focus-visible ~ .checkbox-text:after,
		.checkbox:hover ~ .checkbox-text:after {
			background-color: var(--primary-t-hover);
		}
	}

	/* Dark theme */
	@media (prefers-color-scheme: dark) {
		:root {
			--bg: hsl(var(--hue), 10%, 10%);
			--fg1: hsl(var(--hue), 10%, 90%);
			--fg2: hsl(var(--hue), 10%, 70%);
			--fg3: hsl(var(--hue), 10%, 30%);
			--primary: hsl(var(--hue), 90%, 65%);
			--primary-t-hover: hsla(var(--hue), 90%, 55%, 0.3);
		}
	}
</style>
