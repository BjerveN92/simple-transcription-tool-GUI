<!-- Läge 2: processing -->
<main class="view">
	<header class="header">
		<div class="logo">Logotype</div>
	</header>

	<section class="status">
		<!-- Ersätts senare av en CSS-keyframes-animation -->
		<h1>Transkriberar…</h1>

		<!-- Senare: <time class="timer">00:00</time> och <button>Avbryt</button> -->
	</section>
</main>

<style>
	.view {
		display: flex;
		flex-direction: column;
		max-width: 960px;
		min-height: 100vh;
		margin: 0 auto;
		padding: 1.5rem 2rem;
		box-sizing: border-box;
	}

	.header {
		display: flex;
		align-items: center;
	}

	/* flex: 1 fyller resten av höjden, så att innehållet hamnar mitt på skärmen */
	.status {
		flex: 1;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		gap: 1rem;
	}

	h1 {
		margin: 0;
		font-size: 3rem;
	}
</style>
