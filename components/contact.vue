<template>
  <section id="contact" class="contact">
    <h1 class="contact__title">Contact</h1>

    <div class="contact__form">
      <form type="post" id="contactForm">
        <div class="contact__row">
          <input name="firstName" type="text" class="contact__textfield" placeholder="Voornaam" required>

          <input name="lastName" type="text" class="contact__textfield" placeholder="Achternaam" required>
        </div>
        <div class="contact__row">
          <input name="email" type="email" class="contact__textfield contact__textfield--email" placeholder="Email" required>
        </div>
        <div class="contact__row">
          <textarea type="text" name="message" class="contact__textfield contact__textfield--textarea" placeholder="Bericht" required></textarea>
        </div>
        <div class="contact__row">
          <button type="submit" class="contact__submitbtn">Verzenden</button>
        </div>
      </form>
    </div>
  </section>
</template>

<script>
export default {

}
</script>