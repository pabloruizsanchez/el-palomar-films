<script>
	import logo from '$lib/images/logo.svg';
</script>

<footer class="footer">
	<div class="footer-section logo">
		<img src={logo} alt="El Palomar Films" />
	</div>

	<div class="footer-section contacts">
		<div>
			<strong>SEVILLA (HQ)</strong><br />
			Calle Ejemplo 12<br />
			Sevilla, Spain 41001<br />
			+34 600 000 000<br />
			<a href="mailto:info@elpalomarfilms.com">info@elpalomarfilms.com</a>
		</div>
		<div>
			<strong>GRANADA</strong><br />
			Calle Otra 34<br />
			Granada, Spain 18001<br />
			<a href="mailto:granada@elpalomarfilms.com">granada@elpalomarfilms.com</a>
		</div>
		<div>
			<strong>SHOP ENQUIRIES</strong><br />
			<a href="mailto:shop@elpalomarfilms.com">shop@elpalomarfilms.com</a>
		</div>
	</div>

	<div class="footer-section socials">
		<ul>
			<li><a href="#">INSTAGRAM</a></li>
			<li><a href="#">TWITTER</a></li>
			<li><a href="#">LINKEDIN</a></li>
			<li><a href="#">FACEBOOK</a></li>
		</ul>
		<form on:submit|preventDefault>
			<label for="email">Subscribe to our newsletter</label><br />
			<input type="email" id="email" placeholder="EMAIL" />
			<button type="submit">SUBMIT</button>
		</form>
	</div>
</footer>

<style>
	.footer {
		display: flex;
		justify-content: space-between;
		padding: 4rem 2rem;
		background: #f7f7f7;
		color: #000;
		font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
		font-size: 12px;
		letter-spacing: 0.05em;
	}

	.footer-section {
		flex: 1;
		padding: 0 1rem;
	}

	.logo img {
		max-width: 120px;
	}

	.contacts div {
		margin-bottom: 1.5rem;
	}

	a {
		color: inherit;
		text-decoration: none;
	}

	a:hover {
		text-decoration: underline;
	}

	.socials ul {
		list-style: none;
		padding: 0;
		margin: 0 0 1.5rem 0;
	}

	.socials li {
		margin-bottom: 0.5rem;
	}

	form {
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
	}

	input[type="email"] {
		padding: 0.5rem;
		border: 1px solid #ccc;
		width: 100%;
		font-size: 12px;
	}

	button {
		align-self: flex-start;
		background: none;
		border: none;
		color: inherit;
		font-size: 12px;
		letter-spacing: 0.05em;
		cursor: pointer;
		text-transform: uppercase;
	}
</style>
