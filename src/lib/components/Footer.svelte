<script>
	import logo from '$lib/images/logo-black.svg';
</script>

<footer>
	<div class="footer-container">
		<!-- Logo a la izquierda -->
		<div class="footer-logo">
			<img src={logo} alt="El Palomar Logo" />
		</div>

		<!-- Info centrada -->
		<div class="footer-info">
			<div class="location">
				<h2>Sevilla</h2>
				<a href="mailto:info@elpalomarfilms.com">info@elpalomarfilms.com</a>
				<p>+34 691 55 11 11</p>
			</div>
			<div class="location">
				<h2>Berlin</h2>
				<a href="mailto:hallo@elpalomarfilms.com">hallo@elpalomarfilms.com</a>
				<p>+49 176 83200141</p>
			</div>
		</div>
	</div>
</footer>

<style>
	footer {
		width: 100%;
		padding: 2rem;
		background: white;
		color: black;
		font-size: 0.9rem;
	}

	.footer-container {
		display: flex;
		justify-content: space-between;
		align-items: flex-start;
		flex-wrap: wrap;
		max-width: 1200px;
		margin: 0 auto;
	}

	.footer-logo img {
		width: 120px;
		height: auto;
		opacity: 0.9;
	}

	.footer-info {
		display: flex;
		justify-content: center;
		gap: 4rem;
		flex: 1;
		text-align: left;
	}

	.location h2 {
		font-size: 0.9rem;
		font-weight: bold;
		text-transform: uppercase;
		margin-bottom: 0.5rem;
	}

	.location a {
		color: black;
		text-decoration: underline;
		display: block;
		margin-bottom: 0.25rem;
	}

	.location p {
		margin: 0;
	}

	@media (max-width: 768px) {
		.footer-container {
			flex-direction: column;
			align-items: center;
			text-align: center;
		}

		.footer-info {
			flex-direction: column;
			align-items: center;
			gap: 2rem;
			margin-top: 1.5rem;
		}
	}
</style>
