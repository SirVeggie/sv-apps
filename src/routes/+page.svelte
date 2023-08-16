<script lang="ts">
	import App from '$lib/components/App.svelte';
	import Main from '../lib/components/Main.svelte';

	const shanghai = {
		title: 'shanghai',
		url: 'https://shanghai.sirveggie.com',
		image: 'shanghai.png',
		color: '#333'
	};
	const cards = {
		title: 'cards',
		url: 'https://cards.sirveggie.com',
		image: 'tarot.png',
		color: '#333'
	};
	const abacus = {
		title: 'abacus',
		url: 'https://abacus.sirveggie.com',
		image: 'abacus.png',
		color: '#333'
	};

	const spyfall = {
		title: 'spyfall',
		url: 'https://www.spyfall.app/',
		image: 'spy.jpg',
		color: '#333'
	};
	const codenames = {
		title: 'codenames',
		url: 'https://codenames.game/',
		image: 'codenames.png',
		color: '#333'
	};
</script>

<Main>
	<div class="center">
		<h1>Main Apps</h1>
		<div class="apps">
			<App props={shanghai} />
			<App props={cards} />
			<App props={abacus} />
		</div>

		<h2>Other Apps</h2>
		<div class="apps">
			<App props={spyfall} />
			<App props={codenames} />
		</div>
	</div>
</Main>

<style lang="scss">
    .center {
        max-width: 800px;
        margin: 0 auto;
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    
	h1 {
		font-size: 2rem;
		margin-bottom: 1rem;
		margin-top: 0;
	}

	h2 {
		margin-top: 3rem;
	}

	.apps {
		display: flex;
		gap: 1rem;
		flex-wrap: wrap;
	}
</style>
