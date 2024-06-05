<script lang="ts">
	import BtnSwitchInnerText from './../lib/elements/switch/as_button/BtnSwitchInnerText.svelte';
	import BtnSwitchLabel from './../lib/elements/switch/as_button/BtnSwitchLabel.svelte';
	import BtnSwitchBasic from './../lib/elements/switch/as_button/BtnSwitchBasic.svelte';
	import BtnSwitchInnerIcon from '$lib/elements/switch/as_button/BtnSwitchInnerIcon.svelte';
	import Badge from '$lib/elements/badge/Badge.svelte';
	import BadgeWithIcon from '$lib/elements/badge/BadgeIcon.svelte';
	import Button from '$lib/elements/button/Button.svelte';
	import SwitchLabel from '$lib/elements/switch/as_button/BtnSwitchLabel.svelte';
	// import SwitchIcons from '../lib/elements/switch/as_button/_SwitchIcons.svelte';
	// import New from '$lib/elements/switch/as_button/New.svelte';
	// import BtnSwBasic from '$lib/elements/switch/as_button/SwitchBasic.svelte';
	// import BtnSwLabel from '$lib/elements/switch/as_button/_SwitchLabel.svelte';
	// import SwitchText from '$lib/elements/switch/as_button/_SwitchText.svelte';
	// import SwitchCheckboxLabel from '$lib/elements/switch/as_checkbox/SwitchCheckbox.svelte';
	// import SwitchCheckboxThumbIcon from '$lib/elements/switch/as_checkbox/SwitchCheckboxThumbIcon.svelte';
</script>

<!-- <CheckSwitchBasic /> -->
<div class="flex__c">
	<BtnSwitchBasic is="red" />
	<BtnSwitchLabel is="blue" />
	<BtnSwitchInnerText is="blue"  />
	<BtnSwitchInnerIcon is="pink" />
	<!-- <SwitchBasic is="black" /> -->
	<!-- <SwitchIcons  />
	<SwitchIcons is="red" />
	<SwitchIcons is="blue" /> -->
	<!-- <SwitchCheckboxLabel is="black" disabled /> -->
	<!-- <SwitchCheckboxLabel is="blue" hasLabel /> -->
	<!-- <SwitchCheckboxThumbIcon is="blue" /> -->
</div>
<!-- <New is="red" /> -->

<h1>Badges</h1>
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
		is="red extrasmall"
		onClick={() => {
			console.log('click');
		}}
		>extra small
	</Button>
	<Button
		is="red small"
		onClick={() => {
			console.log('click');
		}}
		>extra small
	</Button>
	<Button
		is="red medium"
		onClick={() => {
			console.log('click');
		}}
		>medium
	</Button>

	<Button
		is="red large"
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
	<BtnSwitchBasic  />
</div>

<p class="sub-category">Toggle Button with Label</p>
<div class="flex__c">
	<BtnSwitchLabel  />
	
</div>

<p class="sub-category">Toggle Button with text</p>
<div class="flex__c">
<BtnSwitchInnerText  />
</div>

<p class="sub-category">Toggle Button with icon</p>
<div class="flex__c">
<BtnSwitchInnerIcon  />
</div>

<hr />

<h1>Checkbox Switch</h1>

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
