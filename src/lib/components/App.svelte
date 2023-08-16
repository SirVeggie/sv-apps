<script lang="ts" context="module">
	export type IApp = {
		title: string;
		url: string;
		color: string;
		image?: string;
	};
</script>

<script lang="ts">
	export let props: IApp;

	let down = false;

	$: style = `--bg: ${props.color};`;
	$: img = !!props.image;

	function handleSpaceDown(e: KeyboardEvent) {
		if (e.key !== ' ') return;
		down = true;
	}

	function handleSpaceUp(e: KeyboardEvent) {
		if (e.key !== ' ') return;
		down = false;
		window.location.href = props.url;
	}

	function handleFocusOut() {
		down = false;
	}
</script>

<a
	{style}
	href={props.url}
	class:down
	class:img
	on:keydown={handleSpaceDown}
	on:keyup={handleSpaceUp}
	on:focusout={handleFocusOut}
>
	{#if img}
		<img src={props.image} alt={props.title} />
	{/if}
	<div class="title">{props.title}</div>
</a>

<style lang="scss">
	a {
		text-decoration: none;
		color: #ddd;
		border-radius: 20px;
		border: 1px solid #ccc2;
		width: 100px;
		height: 100px;
		overflow: hidden;
		position: relative;
		background-color: var(--bg);
		filter: drop-shadow(0 5px 5px #0005);
		transition: transform 0.2s ease, filter 0.2s ease;

		&.img {
			background-color: transparent;
			border: none;
		}

		&:hover {
			transform: translateY(-5px);
			filter: drop-shadow(0 10px 5px #0005);
		}
	}

	img {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	.title {
		position: absolute;
		bottom: 0;
		left: 0;
		right: 0;
		font-size: 12px;
		text-align: center;
		background-color: #222a;
		padding: 5px 0;

		&:first-letter {
			text-transform: capitalize;
		}
        
        :not(.img) & {
            bottom: 50%;
            transform: translateY(50%);
        }
	}
</style>
