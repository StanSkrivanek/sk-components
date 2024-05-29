<script lang="ts">
	import BtnToggleBasic from '$lib/elements/switch/as_button/BtnToggleBasic.svelte';
	import BtnToggleLabel from '$lib/elements/switch/as_button/BtnToggleLabel.svelte';
</script>

<!-- <h1>Badges</h1>
<Badge>Basic</Badge>
<Badge is="red">Error</Badge>
<Badge is="green">Success</Badge>
<Badge is="yellow">Warning</Badge>
<Badge is="blue">info</Badge>
<Badge is="platinum">disabled</Badge>

<hr />

<h1>Buttons</h1>
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

<hr /> -->

<h1>Toggle Button</h1>
<div class="flex__c">
	<BtnToggleBasic is="green" />
	<BtnToggleBasic is="yellow" />
	<BtnToggleBasic is="blue" />
	<BtnToggleBasic is="red" />
	<BtnToggleBasic is="purple" />
</div>

<!-- <h1>Forms Toggle Checkbox</h1>
<div class="flex__c">
	<CheckSwitchBasic />
	<Checkbox_1 />
</div> -->

<h1>Toggle Button with Label</h1>
<div class="flex__c">
	<BtnToggleLabel />
	<BtnToggleLabel is="red" />
	<BtnToggleLabel is="blue" />
</div>

<style>
	.flex__c {
		display: flex;
		gap: 1rem;
		flex-wrap: wrap;
	}
</style>
