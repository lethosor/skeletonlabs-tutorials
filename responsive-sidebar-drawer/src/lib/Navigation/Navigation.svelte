<script lang="ts">
	import { drawerStore } from '@skeletonlabs/skeleton';
	import { page } from '$app/stores';

	function drawerClose(): void {
		drawerStore.close();
	}

	const pages = [
		{path: '/', name: 'Homepage'},
		{path: '/about', name: 'About'},
		{path: '/blog', name: 'Blog'},
		{path: '/contact', name: 'Contact'},
	];
	$: activePath = $page.url.pathname;
</script>

<nav class="list-nav p-4">
	<ul>
		{#each pages as page}
			<li key={page.path}><a href={page.path} class={page.path == activePath ? 'bg-primary-active-token' : null} on:click={drawerClose}>{page.name}</a></li>
		{/each}
	</ul>
</nav>
