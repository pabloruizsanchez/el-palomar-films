<script>
  const contacts = [
    {
      city: 'Sevilla',
      email: 'info@elpalomarfilms.com',
      phone: '+34 691 55 11 11'
    },
    {
      city: 'Berlin',
      email: 'hallo@elpalomarfilms.com',
      phone: '+49 176 83200141'
    }
  ];
</script>

<style>
  .overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    padding: 1rem;
    z-index: 50;
    color: white;
    font-family: sans-serif;
  }

  .logo {
  height: 32px;
}

  .contact-block {
    text-align: right;
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }
</style>

<div class="overlay">
  <img src="/lib/images/logo.svg" alt="El Palomar Films" class="logo" />

  <div class="contact-block">
    {#each contacts as contact}
      <div>
        <strong>{contact.city}</strong><br />
        <a href={`mailto:${contact.email}`} style="color:white">{contact.email}</a><br />
        <a href={`tel:${contact.phone.replace(/\s+/g, '')}`} style="color:white">{contact.phone}</a>
      </div>
    {/each}
  </div>
</div>
