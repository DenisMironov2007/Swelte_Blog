<script>
	import {routes} from '../blog/routes'
</script>

<style>
	.container {
		margin: 50px auto;
		max-width: 800px;
		padding: 0 20px;
	}
	.blogposts {
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-gap: 20px;
	}
	.post {
		border: 1px solid #ddd;
		padding: 10px;
		box-shadow: 0 0 10px #eee;
	}
	.link {
		color: rgb(10, 10, 139);
	}
</style>
	
<svelte:head>
	<title>Blog</title>
</svelte:head>

<div class="container">
	<h1>My articles</h1>
	<div class="blogposts">
		{#each routes as page}
			<div class="post">
				<h2>{page.title}</h2>
				<p>{page.body}</p>
				<div class="redmore">
					<a class="link" href="{`/blog/posts/${page.id}`}">Read more</a>
				</div>
			</div>
		{/each}
	</div>
</div>