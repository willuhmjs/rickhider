<script lang="ts">
	import { metaStore, placeholders } from '$lib/meta';
</script>

<div class="wrapper">
<div class="discord-card" style="border-left: 5px solid {$metaStore.t || $metaStore.d || $metaStore.th ? ($metaStore.th || "#1d1f22"): placeholders.th}">
	<div class="discord-textarea">
		<p class="discord-title">
			{$metaStore.t || $metaStore.d ? $metaStore.t || '' : placeholders.t}
		</p>
		<p class="discord-description">
			{$metaStore.t || $metaStore.d ? $metaStore.d || '' : placeholders.d}
		</p>
	</div>
	<img
		src={$metaStore.t || $metaStore.d || $metaStore.i ? $metaStore.i || '' : placeholders.i}
		alt="OpenGraph"
		on:error={(e) => (e.target.style.display = 'none')}
		on:load={(e) => (e.target.display = 'block')}
	/>
</div>
</div>

<style lang="scss">
	.wrapper {
		display: flex;
		justify-content: center;
	}
	.discord-card {
		background-color: #2c2f33;
		border-radius: 5px;
		box-shadow: 0 0 5px 0 rgba(0, 0, 0, 0.2);
		color: #f2f2f2;
		font-family: 'Whitney', 'Helvetica Neue', Helvetica, Arial, sans-serif;
		font-size: 14px;
		max-width: 350px;
		padding: 10px;
		display: inline-flex;
		gap: 0.8rem;
		margin: 1rem auto;
	}

	.discord-textarea {
		max-width: 100%;
		width: 100%;
		height: 100%;
		overflow: hidden;
		word-wrap: break-word;
	}

	.discord-title {
		font-size: 16px;
		font-weight: 700;
		color: #059ae5;
	}

	.discord-description {
		color: #b9bbbe;
		font-size: 14px;
		font-weight: 400;
		margin: 5px 0;
	}

	img {
		max-width: 80px;
		height: fit-content;
		margin: auto;
	}
</style>
