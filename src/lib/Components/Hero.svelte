<script lang="ts">
	import sample from '$lib/assets/sample.png';

	let showDonatePopup = false;

	const cards = [
		{
			title: 'BECOME THE VOICE',
			desc: 'True journalism strives when the society participates. This election season, bring us original stories from across Assam and get compensated for the same.',
			buttonText: 'REGISTER',
			link: 'https://example.com/register-link'
		},
		{
			title: 'SUPPORT THE CAUSE',
			desc: 'This whole effort will collapse without your support. Help us pay the journalists and our editors so we can cover Assam Elections 2026 without bias.',
			buttonText: 'DONATE',
			link: null
		}
	];

	function handleButtonClick(card: (typeof cards)[0]) {
		if (card.buttonText === 'DONATE') {
			showDonatePopup = true;
		} else if (card.link) {
			window.open(card.link, '_blank');
		}
	}
</script>

<main class="page-wrapper">
	<section class="hero">
		<div class="video-container">
			<iframe
				src="https://www.youtube.com/embed/aduJw2fiDAQ"
				title="DHIMAN GOES IRL (🇹🇭THAILAND) - TRAILER"
				frameborder="0"
				allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
				allowfullscreen
			></iframe>
		</div>

		<div class="headings-container">
			<span class="hashtag">#ASSAMYOUTH2026</span>
			<h1 class="main-title">
				THE YOUTH IS AWARE. <br />
				<span class="highlight-gold">THE YOUTH IS WATCHING.</span>
			</h1>
			<p class="subtitle">Live Everyday @ 7:30PM on YouTube</p>
		</div>

		<button
			class="btn btn-primary btn-channel"
			on:click={() => window.open('https://www.youtube.com/@bondhustreams', '_blank')}
		>
			<div class="avatar">
				<img src={sample} alt="profile" />
			</div>
			<span>bondhustreams</span>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				class="arrow-icon"
				fill="none"
				viewBox="0 0 24 24"
				stroke="currentColor"
				stroke-width="3"
			>
				<path stroke-linecap="round" stroke-linejoin="round" d="M17 8l4 4m0 0l-4 4m4-4H3" />
			</svg>
		</button>
	</section>

	<section class="cards-grid">
		{#each cards as card}
			<div class="card">
				<div class="card-image-placeholder">
					<img src={sample} alt="card visual" class="card-img" />
				</div>
				<h2 class="card-title">{card.title}</h2>
				<p class="card-desc">{card.desc}</p>
				<button class="btn btn-primary btn-small" on:click={() => handleButtonClick(card)}>
					{card.buttonText}
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="arrow-icon"
						fill="none"
						viewBox="0 0 24 24"
						stroke="currentColor"
						stroke-width="3"
					>
						<path stroke-linecap="round" stroke-linejoin="round" d="M17 8l4 4m0 0l-4 4m4-4H3" />
					</svg>
				</button>
			</div>
		{/each}
	</section>

	<section class="content-section">
		<h2 class="section-heading">A REVOLUTION IS HERE</h2>
		<div class="prose">
			<p>
				Time and again, we, the youth of Assam have stayed quiet on politics. 2026, however, is our
				turning point. It's our time to rise, choose progress, demand fairness, and
				<span class="text-highlight">vote for change.</span>
			</p>
			<p>
				Support <span class="text-highlight">bondhustreams</span> in covering the 2026 elections in a
				fair, non-biased, comprehensive, and entertaining way that resonates with the young population
				of Assam.
			</p>
			<p><span class="text-highlight tag">No drama, no hate-mongering.</span></p>
			<p>
				Only rational conversations, constructive criticism, asking for transparency,
				accountability, and voting for candidates who listen to the
				<span class="text-highlight">voice of young Assam.</span>
			</p>
		</div>

		<div class="footer-meta">
			<p class="credits">
				An initiative by bondhustreams & dhimanstreams<br />for the youth of Assam.
			</p>
			<div class="share-links">
				<button class="link-btn">Share on Whatsapp</button>
				<button class="link-btn">Share on your Insta Story</button>
				<button class="link-btn">Copy Link</button>
			</div>
		</div>
	</section>

	<div>
		{#if showDonatePopup}
			<div class="modal-overlay" on:click|self={() => (showDonatePopup = false)}>
				<div class="modal-wrapper">
					<div class="modal-content">
						<img src={sample} alt="Donate QR or Info" class="modal-img" />
						<div class="modal-text">
							<h3>SEND GAHORI BHAT</h3>
							<p>
								Scan the code above or use UPI: <b>bondhu@upi</b>. Your contribution helps us devour
								gahori bhat.
							</p>
						</div>
					</div>
					<button class="close-btn" on:click={() => (showDonatePopup = false)}>✕</button>
				</div>
			</div>
		{/if}
	</div>
</main>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Akshar:wght@300..700&family=Faustina:ital,wght@0,300..800;1,300..800&display=swap');

	:global(body) {
		background-color: #000;
		margin: 0;
		padding: 0;
		color: #ffffff;
		font-size: 18px;
		letter-spacing: -0.01em;
	}

	.page-wrapper {
		min-height: 100vh;
		padding: 0 1.5rem 5rem 1.5rem;
	}

	@media (min-width: 768px) {
		.page-wrapper {
			padding-left: 2.5rem;
			padding-right: 2.5rem;
		}
	}

	.hero {
		max-width: 60rem;
		margin: 0 auto;
		display: flex;
		flex-direction: column;
		align-items: center;
		text-align: center;
		padding-top: 3rem;
	}

	.video-container {
		position: relative;
		margin-bottom: 2.5rem;
		aspect-ratio: 16 / 9;
		width: 100%;
		overflow: hidden;
		border-radius: 1rem;
		background-color: #0b0b1a;
		outline: 5px solid #ffffff;
		outline-offset: -2px;
	}

	.video-container iframe {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		border-radius: 1rem;
	}

	.headings-container {
		margin-bottom: 2rem;
		font-family: 'Akshar';
	}

	.hashtag {
		display: inline-block;
		margin-bottom: 0.75rem;
		background-color: #fd2a2a;
		padding: 0.2rem 0.5rem;
		font-size: 1.75rem;
		font-weight: 700;
		letter-spacing: -0.03em;
	}

	.main-title {
		font-size: 2.25rem;
		line-height: 1.1;
		font-weight: 700;
		letter-spacing: -0.04em;
		text-transform: uppercase;
		margin: 0;
	}

	@media (min-width: 768px) {
		.main-title {
			font-size: 4rem;
			line-height: 0.9;
		}
	}

	.highlight-gold {
		color: #f4bb12;
	}

	.subtitle {
		margin-top: 1.25rem;
		font-size: 1.5rem;
		font-weight: 700;
		letter-spacing: -0.02em;
	}

	.btn {
		display: flex;
		align-items: center;
		gap: 1rem;
		border-radius: 0.75rem;
		border: none;
		color: white;
		font-weight: 700;
		cursor: pointer;
		font-family: 'Akshar';
		letter-spacing: -0.01em;
		font-size: 1.1rem;
	}

	.btn-primary {
		background-color: #fd2a2a;
	}
	.btn-channel {
		margin: 0 auto 5rem auto;
		padding: 0.75rem 1.5rem;
	}
	.btn-small {
		width: fit-content;
		padding: 1rem 2rem;
		font-size: 1.1rem;
	}

	.avatar {
		height: 2.5rem;
		width: 2.5rem;
		border-radius: 9999px;
		border: 1px solid rgba(255, 255, 255, 0.2);
	}
	.arrow-icon {
		width: 1.25rem;
		height: 1.25rem;
		transform: rotate(315deg);
	}

	.cards-grid {
		max-width: 70rem;
		margin: 0 auto 6rem auto;
		display: grid;
		grid-template-columns: 1fr;
		gap: 3.5rem;
	}

	@media (min-width: 768px) {
		.cards-grid {
			grid-template-columns: 1fr 1fr;
		}
	}

	.card-title {
		margin-bottom: 1rem;
		font-size: 1.85rem;
		font-weight: 900;
		letter-spacing: -0.035em;
		text-transform: uppercase;
		font-family: 'Akshar';
	}

	.card-desc {
		color: #fff;
		font-size: 1.25rem;
		line-height: 1.4;
		font-family: 'Faustina';
		font-weight: 300;
		letter-spacing: -0.015em;
		max-width: 400px;
		margin-bottom: 2rem;
	}

	.content-section {
		max-width: 50rem;
		margin: 0 auto;
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.section-heading {
		font-size: 2.25rem;
		font-weight: 900;
		letter-spacing: -0.03em;
		text-transform: uppercase;
		margin-bottom: 1rem;
		font-family: 'Akshar';
	}

	.prose {
		color: #ffffff;
		font-size: 1.3rem;
		line-height: 1.5;
		font-family: 'Faustina';
		font-weight: 400;
		letter-spacing: -0.01em;
		max-width: 450px;
	}

	.text-highlight {
		background-color: #fd2a2a;
		padding: 0 0.35rem;
	}
	.tag {
		font-size: 1rem;
		text-transform: uppercase;
		font-weight: 700;
		letter-spacing: -0.02em;
	}

	.credits {
		margin-bottom: 2.5rem;
		font-size: 1rem;
		color: #9ca3af;
		font-family: 'Akshar';
		letter-spacing: -0.01em;
	}

	.share-links {
		display: flex;
		flex-wrap: wrap;
		gap: 2rem;
		font-size: 13px;
		font-weight: 700;
		text-transform: uppercase;
		font-family: 'Akshar';
		letter-spacing: 0.02em;
	}

	.link-btn {
		color: rgba(255, 255, 255, 0.9);
		text-underline-offset: 6px;
	}

	.modal-content {
		max-width: 450px;
		padding: 2.5rem;
	}

	.modal-text h3 {
		font-size: 1.75rem;
		letter-spacing: -0.02em;
	}
	.modal-text p {
		font-size: 1.2rem;
		letter-spacing: -0.01em;
	}
</style>
