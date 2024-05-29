<script lang="ts">
	import Badge from '$lib/components/Badge.svelte';
	import Button from '$lib/components/Button.svelte';
	import ToggleBasic from '$lib/components/ToggleBasic.svelte';

	
</script>

<h1>Badges</h1>
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

<hr />

<h1>Toggle</h1>
<ToggleBasic is="blue" />

<style>
	.flex__c {
		display: flex;
		gap: 1rem;
		flex-wrap: wrap;
	}
</style>
