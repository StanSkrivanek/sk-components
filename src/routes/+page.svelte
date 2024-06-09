<script lang="ts">
	import CheckboxGroup from '../../unused/CheckboxGroup-2.svelte';
	// import CheckboxTest from '$lib/elements/checkbox/CheckboxTest.svelte';
	// import Badge from '$lib/elements/badge/Badge.svelte';
	// import BadgeWithIcon from '$lib/elements/badge/BadgeIcon.svelte';
	// import Button from '$lib/elements/button/Button.svelte';
	// import BtnSwitchInnerIcon from '$lib/elements/button/as_switch/BtnSwitchInnerIcon.svelte';

	// import BtnSwitchBasic from '$lib/elements/button/as_switch/BtnSwitchBasic.svelte';
	// import BtnSwitchInnerText from '$lib/elements/button/as_switch/BtnSwitchInnerText.svelte';
	// import BtnSwitchLabel from '$lib/elements/button/as_switch/BtnSwitchLabel.svelte';
</script>

<div class="flex__c">
	<!-- stuff -->
	<!-- <CheckboxSwitch is="red pill" showState>WI-FI</CheckboxSwitch> -->
	<!-- <Checkbox is="red pill" showState checked role="switch" /> -->
	<form action="">
		<CheckboxGroup />
		<!-- <div class="checkbox-group"> -->
			<!-- <CheckboxTest label="Select all" isParent />
			<CheckboxTest name="wifi" label="wifi" checked />
			<CheckboxTest name="ethernet" label="ethernet" />
			<CheckboxTest name="bluetooth" label="bluetooth" /> -->
			<!-- <ul>
				<li><CheckboxTest name="connection" label="wifi" /></li>
				<li><CheckboxTest name="connection" label="ethernet" /></li>
			</ul> -->
		<!-- </div> -->
	</form>
	<!-- <CheckboxTest name="connection" value="wi-fi" isParent label="wifi" /> -->
	<!-- <CheckboxTest name="connection" value="ethernet" isParent label="ethernet" /> -->
</div>

<!-- <div class="flex__c"> -->
<!-- stuff -->
<!-- <Checkbox checked />
	<Checkbox is="red" hasLabel />
	<Checkbox is="black" />
	<Checkbox disabled checked /> -->
<!-- </div> -->

<!-- <h1>Badges</h1>
<p class="sub-category">Badge size</p>

<div class="flex__c">
	<Badge is="black">basic</Badge>
	<Badge is="black medium">medium</Badge>
</div>
<p class="sub-category">Badge style</p>
<div class="flex__c">
	<Badge is="black">basic</Badge>
	<Badge is="black outline">outline</Badge>
	<Badge is="black pill">pill</Badge>
	<Badge is="black pill outline">pill outline</Badge>
</div>

<p class="sub-category">Badge with Icon</p>

<div class="flex__c">
	<BadgeWithIcon
		is="black "
		onClick={() => {
			console.log('click');
		}}>basic</BadgeWithIcon
	>
	<BadgeWithIcon
		is="black outline"
		onClick={() => {
			console.log('click');
		}}>outline</BadgeWithIcon
	>
	<BadgeWithIcon
		is="black pill"
		onClick={() => {
			console.log('click');
		}}>pill</BadgeWithIcon
	>
	<BadgeWithIcon
		is="black pill outline"
		onClick={() => {
			console.log('click');
		}}
	>
		pill outline</BadgeWithIcon
	>
</div>

<p class="sub-category">Badge color</p>
<div class="flex__c">
	<Badge is="red">red</Badge>
	<Badge is="orange">orange</Badge>
	<Badge is="yellow">yellow</Badge>
	<Badge is="green">green</Badge>
	<Badge is="cyan">cyan</Badge>
	<Badge is="blue">blue</Badge>
	<Badge is="purple">purple</Badge>
	<Badge is="pink">pink</Badge>
	<Badge is="platinum">platinum</Badge>
	<Badge is="steel">steel</Badge>
	<Badge is="black">black</Badge>
</div>
<hr />

<h1>Buttons</h1>

<p class="sub-category">Button size</p>

<div class="flex__c">
	<Button
		is="red xs"
		onClick={() => {
			console.log('click');
		}}
		>extra small
	</Button>
	<Button
		is="red sm"
		onClick={() => {
			console.log('click');
		}}
		>small
	</Button>
	<Button
		is="red "
		onClick={() => {
			console.log('click');
		}}
		>basic
	</Button>
	<Button
		is="red md"
		onClick={() => {
			console.log('click');
		}}
		>medium
	</Button>

	<Button
		is="red lg"
		onClick={() => {
			console.log('click');
		}}
		>large
	</Button>
</div>

<p class="sub-category">Button colors</p>

<div class="flex__c">
	<Button
		is="red "
		onClick={() => {
			console.log('click');
		}}
		>Button
	</Button>
	<Button
		is="orange"
		onClick={() => {
			console.log('click');
		}}
		>Button
	</Button>
	<Button
		is="yellow"
		onClick={() => {
			console.log('click');
		}}
		>Button
	</Button>
	<Button
		is="green"
		onClick={() => {
			console.log('click');
		}}
		>Button
	</Button>
	<Button
		is="cyan"
		onClick={() => {
			console.log('click');
		}}
		>Button
	</Button>
	<Button
		is="blue"
		onClick={() => {
			console.log('click');
		}}
		>Button
	</Button>
	<Button
		is="pink"
		onClick={() => {
			console.log('click');
		}}
		>Button
	</Button>
	<Button
		is="purple"
		onClick={() => {
			console.log('click');
		}}
		>Button
	</Button>
	<Button
		is="platinum"
		onClick={() => {
			console.log('click');
		}}
		>Button
	</Button>
	<Button
		onClick={() => {
			console.log('click');
		}}
		>Button
	</Button>
	<Button
		is="black"
		onClick={() => {
			console.log('click');
		}}
		>Button
	</Button>
</div>

<hr />

<h1>Button Switch</h1>

<p class="sub-category">Toggle Button</p>
<div class="flex__c">
	<BtnSwitchBasic />
</div>

<p class="sub-category">Toggle Button with Label</p>
<div class="flex__c">
	<BtnSwitchLabel />
</div>

<p class="sub-category">Toggle Button with text</p>
<div class="flex__c">
	<BtnSwitchInnerText />
</div>

<p class="sub-category">Toggle Button with icon</p>
<div class="flex__c">
	<BtnSwitchInnerIcon />
</div>

<hr />

<h1>Checkbox Switch</h1> -->

<style>
	h1 {
		font-family: var(--fw-black);
	}
	.flex__c {
		display: flex;
		align-items: center;
		/* justify-content: center; */
		gap: 1rem;
		flex-wrap: wrap;
		margin-bottom: 3rem;
	}
	.sub-category {
		color: hsl(var(--hsl-gray));
		font-family: var(--fw-medium);
		margin-bottom: 0.5rem;
		text-transform: uppercase;
	}
</style>
