<template>
  <section id="header" class="header">
    <div class="header__container">
      <div class="header__intro">
        <div id="headingPicture" class="img-placeholder">&nbsp;</div>
        <h1 class="header__text header__text--big">Max Huber</h1>
        <vue-typer
          class="header__text header__text--green header__text--shadow"
          text="Webdeveloper"
        ></vue-typer>
      </div>
      <div class="header__quotebox">
        <h2 class="header__quote">{{ quote.text }}</h2>
        <p class="header__quote--author">{{ quote.author }}</p>
      </div>
    </div>
  </section>
</template>

<script>
import quotes from '~/static/json/quotes.json'

export default {
  name: 'header',
  data() {
    return {
      quote: {}
    }
  },
  mounted() {
    this.getQuote()
  },
  methods: {
    getQuote() {
      const index = Math.floor((Math.random() * 9));
      this.quote = quotes[index]
    }
  }
}
</script>