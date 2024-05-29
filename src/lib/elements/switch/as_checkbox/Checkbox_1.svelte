<script lang="ts">
	// import type { Snippet } from 'svelte';
	export const { is, children } = $props();
</script>

<label for="switch" class="gui-switch">
	<input type="checkbox" role="switch" id="form-switch" />
	Label text
</label>
