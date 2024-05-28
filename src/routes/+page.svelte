<script lang="ts">
	import Badge from '$lib/components/Badge.svelte';
	import Button from '$lib/components/Button.svelte';
</script>

<h1>Badges</h1>
<Badge is="red">Error</Badge>
<Badge is="green">Success</Badge>
<Badge is="blue">info</Badge>
<Badge is="disabled">disabled</Badge>
<h1>Buttons</h1>
<Button is="large orange outline">standard</Button>
<Button is="orange">standard</Button>
<Button is="medium orange">standard</Button>
<Button is="small orange pill">standard</Button>

