<script>
	import Timeline from '$lib/Timeline.svelte';
	import data from '$lib/data.json';
</script>

<div class="container py-3">
	<Timeline {data} />
</div>
