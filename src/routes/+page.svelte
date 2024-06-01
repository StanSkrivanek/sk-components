<script lang="ts">
	import Badge from '$lib/elements/badge/Badge.svelte';
	import BadgeWithIcon from '$lib/elements/badge/BadgeIcon.svelte';
	import BtnSwBasic from '$lib/elements/switch/as_button/SwitchBasic.svelte';
	import BtnSwLabel from '$lib/elements/switch/as_button/SwitchLabel.svelte';
	import SwitchText from '$lib/elements/switch/as_button/SwitchText.svelte';
	import Button from './../lib/elements/button/Button.svelte';
</script>

<h1>Badges</h1>
<h2>Badge basic</h2>
<div class="flex__c">
	<Badge is=" redpill outline">Basic</Badge>
	<Badge is="red">Error</Badge>
	<Badge is="green">Success</Badge>
	<Badge is="yellow">Warning</Badge>
	<Badge is="blue">info</Badge>
	<Badge is="platinum">disabled</Badge>
</div>

<h2>Badge with Icon</h2>
<div class="flex__c">
	<BadgeWithIcon is="red pill outline">Basic</BadgeWithIcon>
	<BadgeWithIcon is="blue ">Basic</BadgeWithIcon>
	<BadgeWithIcon is="green medium">Basic</BadgeWithIcon>
	<BadgeWithIcon is="">Basic</BadgeWithIcon>
</div>

<hr />

<h1>Buttons</h1>

<h2>Button basic</h2>
<div class="flex__c">
	<Button>basic</Button>
	<Button is="red">red</Button>
	<Button is="orange">orange</Button>
	<Button is="yellow">yellow</Button>
	<Button is="green">green</Button>
	<Button is="cyan">cyan</Button>
	<Button is="blue">blue</Button>
	<Button is="pink">pink</Button>
	<Button is="purple">purple</Button>
	<Button is="platinum">platinum</Button>
	<Button is="black">black</Button>
</div>

<hr />

<h1>Switch Buttons</h1>

<h2>Toggle Button</h2>
<div class="flex__c">
	<BtnSwBasic is="green" />
	<BtnSwBasic is="yellow" />
	<BtnSwBasic is="blue" />
	<BtnSwBasic is="red" />
	<BtnSwBasic is="purple" />
</div>

<h2>Toggle Button with Label</h2>
<div class="flex__c">
	<BtnSwLabel />
	<BtnSwLabel is="red" />
	<BtnSwLabel is="blue" />
</div>

<h2>Toggle Button with text</h2>
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
</style>
