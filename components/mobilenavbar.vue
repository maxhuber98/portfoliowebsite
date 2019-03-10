<template>
  <section id="mobileNav" class="mobilenavbar__container">
    <a href="javascript:void(0);" id="hamburger-icon" @click="toggleHamburger">
      <span class="line line-1"></span>
      <span class="line line-2"></span>
      <span class="line line-3"></span>
    </a>

    <ul id="mobileNav-list" class="mobilenavbar__list">
      <li class="mobilenavbar__item">
        <a href="#" @click="toggleHamburger">Home</a>
      </li>
      <li class="mobilenavbar__item">
        <a href="#about" @click="toggleHamburger">Over mij</a>
      </li>
      <li class="mobilenavbar__item">
        <a href="#skills" @click="toggleHamburger">Skills</a>
      </li>
      <li class="mobilenavbar__item">
        <a href="#contact" @click="toggleHamburger">Contact</a>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      toggled: false
    }
  },
  methods: {
    toggleHamburger() {
      var hamburger = document.getElementById("hamburger-icon")
      hamburger.classList.toggle('active')

      var mobileNavContainer = document.getElementById("mobileNav")
      var mobileNavList = document.getElementById("mobileNav-list")

      if (!this.toggled) {
        mobileNavContainer.classList.add("mobilenavbar__container--active")
        mobileNavList.classList.add("mobilenavbar__list--active")
        mobileNavContainer.classList.remove("mobilenavbar__container--inactive")
        mobileNavList.classList.remove("mobilenavbar__list--inactive")

        this.toggleSlideforListChildren()

        this.toggled = true
      } else {
        mobileNavContainer.classList.remove("mobilenavbar__container--active")
        mobileNavList.classList.remove("mobilenavbar__list--active")
        mobileNavContainer.classList.add("mobilenavbar__container--inactive")
        mobileNavList.classList.add("mobilenavbar__list--inactive")

        this.toggleSlideforListChildren()

        this.toggled = false
      }
    },
    toggleSlideforListChildren() {
      var mobileNavList = document.getElementById("mobileNav-list")

      mobileNavList.children[0].classList.toggle("mobilenavbar__item--slideinleft")
      mobileNavList.children[2].classList.toggle("mobilenavbar__item--slideinleft")
      mobileNavList.children[1].classList.toggle("mobilenavbar__item--slideinright")
      mobileNavList.children[3].classList.toggle("mobilenavbar__item--slideinright")
    }
  }
}
</script>