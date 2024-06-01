<script lang="ts">
	import Badge from '$lib/elements/badge/Badge.svelte';
	import BadgeWithIcon from '$lib/elements/badge/BadgeIcon.svelte';
	import BtnSwBasic from '$lib/elements/switch/as_button/SwitchBasic.svelte';
	import BtnSwLabel from '$lib/elements/switch/as_button/SwitchLabel.svelte';
	import SwitchText from '$lib/elements/switch/as_button/SwitchText.svelte';
	import Button from '$lib/elements/button/Button.svelte';
</script>

<h1>Badges</h1>
<h2 class="sub-category">Badge basic</h2>
<div class="flex__c">
	<Badge is=" redpill outline" label="Basic"/>
	<Badge is="red" label="red"/>
	<Badge is="green" label="green"/>
	<Badge is="yellow" label="yellow"/>
	<Badge is="blue" label="blue"/>
	<Badge is="platinum" label="platinum"/>
</div>

<h2 class="sub-category">Badge with Icon</h2>
<div class="flex__c">
	<BadgeWithIcon is="red pill outline" onClick={() => {console.log("click")}} label="red"/>
	<BadgeWithIcon is="blue pill" onClick={() => {console.log("click")}} label="info"/>
	<BadgeWithIcon is="green medium" onClick={() => {console.log("click")}} label="success"/>
	<BadgeWithIcon is=" medium"  onClick={() => {console.log("click")}} label="basic"/>
</div>

<hr />

<h1>Buttons</h1>

<h2 class="sub-category">Button basic</h2>
<div class="flex__c">
	<Button onClick={() => {console.log("click")}} label="button"/>
	<Button is="red" onClick={() => {console.log("click")}} label="button"/>
	<Button is="orange" onClick={() => {console.log("click")}} label="button"/>
	<Button is="yellow" onClick={() => {console.log("click")}} label="button"/>
	<Button is="green" onClick={() => {console.log("click")}} label="button"/>
	<Button is="cyan" onClick={() => {console.log("click")}} label="button"/>
	<Button is="blue" onClick={() => {console.log("click")}} label="button"/>
	<Button is="pink" onClick={() => {console.log("click")}} label="button"/>
	<Button is="purple" onClick={() => {console.log("click")}} label="button"/>
	<Button is="platinum" onClick={() => {console.log("click")}} label="button"/>
	<Button is="black" onClick={() => {console.log("click")}} label="button"/>
</div>

<hr />

<h1>Switch Buttons</h1>

<h2 class="sub-category">Toggle Button</h2>
<div class="flex__c">
	<BtnSwBasic is="green" />
	<BtnSwBasic is="yellow" />
	<BtnSwBasic is="blue" />
	<BtnSwBasic is="red" />
	<BtnSwBasic is="purple" />
</div>

<h2 class="sub-category">Toggle Button with Label</h2>
<div class="flex__c">
	<BtnSwLabel />
	<BtnSwLabel is="red" />
	<BtnSwLabel is="blue" />
</div>

<h2 class="sub-category">Toggle Button with text</h2>
<div class="flex__c">
	<SwitchText>Basic</SwitchText>
	<SwitchText is="blue">Basic</SwitchText>
	<SwitchText is="red">Basic</SwitchText>
	<SwitchText is="orange">Basic</SwitchText>
</div>

<style>
	h1 {
		font-family: var(--fw-black);
	}
	.flex__c {
		display: flex;
		gap: 1rem;
		flex-wrap: wrap;
		margin-bottom: 1rem;
	}
	.sub-category{
		color: hsl(var(--hsl-gray));
		
	}
</style>
