<script>
  import logo from '$lib/images/logo.svg';
</script>

<div class="about-page">
  <!-- Logo grande y centrado -->
  <div class="logo-container">
    <img src={logo} alt="El Palomar Films logo" />
  </div>

  <!-- Texto descriptivo -->
  <div class="about-text">
    <p>
      El Palomar Films is a creative studio based in Andalusia, working with honesty, sensitivity, and a strong personal vision.
      <br /><br />
      We are not an agency. We are creators. We tell stories that connect with what’s real — with people, with emotions, and with the place we come from.
      <br /><br />
      We believe in the power of well-crafted storytelling without artifice, with truth.
      From the South of Spain, we offer a new perspective on our culture — far from cliché, close to emotion.
      <br /><br />
      We embrace modern concepts that never forget where we come from or where we stand.
      <br /><br />
      We are responsible for every step of our productions: from casting, scriptwriting, and art direction, to original music. This allows us to deliver truly unique, tailor-made pieces, with a recognizable signature and a language of our own.
    </p>
  </div>

  <!-- Dirección de contacto -->
  <div class="contact-info">
    <a href="mailto:info@elpalomarfilms.com">info@elpalomarfilms.com</a>
  </div>
</div>

<style>
  .about-page {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 10vh 5vw;
    background: white;
    color: black;
  }

  .logo-container {
    width: 200px;
    max-width: 60vw;
    margin-bottom: 4rem;
  }

  .logo-container img {
    width: 100%;
    height: auto;
    display: block;
  }

  .about-text {
    max-width: 700px;
    text-align: center;
    line-height: 1.6;
    font-size: 1.1rem;
    margin-bottom: 3rem;
  }

  .contact-info {
    font-family: monospace;
    font-size: 1rem;
    text-align: center;
  }

  .contact-info a {
    color: black;
    text-decoration: none;
  }

  .contact-info a:hover {
    text-decoration: underline;
  }
</style>
