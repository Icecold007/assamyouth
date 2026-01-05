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
				Time and again, we, the youth of Assam have stayed quiet on<br />politics. 2026, however, is
				our turning point. It's our time to<br />rise, choose progress, demand fairness, and
				<span class="text-highlight">vote for change.</span>
			</p>
			<p>
				Support <span class="text-highlight">bondhustreams</span> in covering the 2026 elections in
				a<br />fair, non-biased, comprehensive, and entertaining way that<br />resonates with the
				young population of Assam.
			</p>
			<p><span class="text-highlight tag">No drama, no hate-mongering.</span></p>
			<p>
				Only rational conversations, constructive criticism, asking<br />for transparency,
				accountability, and voting for candidates<br />who listen to the
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
				<div class="modal-content">
					<button class="close-btn" on:click={() => (showDonatePopup = false)}>&times;</button>
					<img src={sample} alt="Donate QR or Info" class="modal-img" />
					<div class="modal-text">
						<h3>SEND GAHORI BHAT</h3>
						<p>
							Scan the code above or use UPI: <b>bondhu@upi</b>. Your contribution helps us devour
							gahori bhat.
						</p>
					</div>
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
		max-width: 56rem;
		margin: 0 auto;
		display: flex;
		flex-direction: column;
		align-items: center;
		text-align: center;
		padding-top: 2.5rem;
	}

	.video-container {
		position: relative;
		margin-bottom: 2rem;
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
		margin-bottom: 1.5rem;
		font-family: 'Akshar';
	}
	.hashtag {
		display: inline-block;
		margin-bottom: 0.5rem;
		background-color: #fd2a2a;
		padding: 0rem 0.25rem;
		font-size: 1.5rem;
		font-weight: 600;
		letter-spacing: -0.05em;
	}
	.main-title {
		font-size: 1.875rem;
		line-height: 0.8;
		font-weight: 600;
		letter-spacing: -0.025em;
		text-transform: uppercase;
		margin: 0;
	}
	@media (min-width: 768px) {
		.main-title {
			font-size: 3rem;
		}
	}
	.highlight-gold {
		color: #f4bb12;
	}
	.subtitle {
		margin-top: 1rem;
		font-size: 1.125rem;
		font-weight: 700;
		letter-spacing: -0.025em;
	}

	.btn {
		display: flex;
		align-items: center;
		gap: 0.75rem;
		border-radius: 0.75rem;
		border: none;
		color: white;
		font-weight: 700;
		cursor: pointer;
		transition: background-color 0.2s;
		text-decoration: none;
		font-family: 'Akshar';
	}
	.btn-primary {
		background-color: #fd2a2a;
	}
	.btn-primary:hover {
		background-color: #e02424;
	}
	.btn-channel {
		margin: 0 auto 4rem auto;
		padding: 0.5rem 1rem;
	}
	.btn-small {
		width: fit-content;
		padding: 0.75rem 1.5rem;
		font-size: 0.875rem;
	}

	.avatar {
		height: 2rem;
		width: 2rem;
		overflow: hidden;
		border-radius: 9999px;
		border: 1px solid rgba(255, 255, 255, 0.2);
		background-color: #374151;
	}
	.avatar img {
		width: 100%;
		height: 100%;
	}
	.arrow-icon {
		width: 1rem;
		height: 1rem;
		transform: rotate(315deg);
	}

	.cards-grid {
		max-width: 64rem;
		margin: 0 auto 5rem auto;
		display: grid;
		grid-template-columns: 1fr;
		gap: 2.5rem;
	}
	@media (min-width: 768px) {
		.cards-grid {
			grid-template-columns: 1fr 1fr;
		}
	}

	.card {
		display: flex;
		flex-direction: column;
	}
	.card-image-placeholder {
		margin-bottom: 1.5rem;
		aspect-ratio: 16 / 9;
		width: 100%;
		border-radius: 1rem;
		background-color: #d9d9d9;
		overflow: hidden;
	}
	.card-img {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}
	.card-title {
		margin-bottom: 0.75rem;
		font-size: 1.5rem;
		font-weight: 900;
		letter-spacing: -0.05em;
		text-transform: uppercase;
		margin-top: 0;
		font-family: 'Akshar';
	}
	.card-desc {
		color: #fff;
		font-size: 1rem;
		line-height: 1;
		font-family: 'Faustina';
		font-weight: 300;
		letter-spacing: -1px;
		max-width: 350px;
		margin-bottom: 1.5rem;
	}

	.content-section {
		max-width: 42rem;
		margin: 0 auto;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.section-heading {
		font-size: 1.875rem;
		font-weight: 900;
		letter-spacing: -0.05em;
		text-transform: uppercase;
		margin-bottom: 0.3rem;
		font-family: 'Akshar';
		margin-right: 100px;
	}
	@media (max-width: 768px) {
		.section-heading {
			margin-right: 0;
		}
	}
	.prose {
		color: #ffffff;
		font-size: 1.03rem;
		line-height: 1;
		font-family: 'Faustina';
		font-weight: 300;
		letter-spacing: -1px;
		max-width: 350px;
	}
	.text-highlight {
		background-color: #fd2a2a;
		padding: 0 0.25rem;
	}
	.tag {
		font-size: 0.875rem;
		text-transform: uppercase;
	}

	.footer-meta {
		padding-top: 1rem;
		margin-right: 60px;
	}
	.credits {
		margin-bottom: 2rem;
		font-size: 0.75rem;
		color: #6b7280;
		font-family: 'Akshar';
	}
	.share-links {
		display: flex;
		flex-wrap: wrap;
		gap: 1.5rem;
		font-size: 10px;
		font-weight: 700;
		text-transform: uppercase;
		font-family: 'Akshar';
		justify-content: center;
	}
	.link-btn {
		background: none;
		border: none;
		color: rgba(255, 255, 255, 0.8);
		cursor: pointer;
		text-decoration: underline;
		text-underline-offset: 4px;
	}

	.modal-overlay {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background: rgba(0, 0, 0, 0.85);
		display: flex;
		align-items: center;
		justify-content: center;
		z-index: 1000;
	}
	.modal-content {
		background: #111;
		padding: 2rem;
		border-radius: 1.5rem;
		max-width: 400px;
		width: 90%;
		position: relative;
		border: 1px solid #333;
		text-align: center;
		font-family: 'Akshar';
	}
	.close-btn {
		position: absolute;
		top: 1rem;
		right: 1rem;
		background: none;
		border: none;
		color: white;
		font-size: 2rem;
		cursor: pointer;
	}
	.modal-img {
		width: 100%;
		border-radius: 1rem;
		margin-bottom: 1.5rem;
	}
	.modal-text h3 {
		color: #f4bb12;
		margin-bottom: 0.5rem;
		text-transform: uppercase;
	}
	.modal-text p {
		font-family: 'Faustina';
		line-height: 1.4;
		color: #ccc;
	}
</style>
