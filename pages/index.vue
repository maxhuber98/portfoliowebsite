<template>
  <div>
    <navbar></navbar>
    <sticky-nav></sticky-nav>
    <mobile-nav></mobile-nav>
    <heading></heading>
    <about></about>
    <skills></skills>
    <contact></contact>
  </div>
</template>

<script>
import navbar from '@/components/navbar'
import stickyNav from '@/components/stickynavbar'
import mobileNav from '@/components/mobilenavbar'
import heading from '@/components/header'
import about from '@/components/about'
import skills from '@/components/skills'
import contact from '@/components/contact'

export default {
  data() {
    return {
      sticky: false
    }
  },
  components: {
    navbar,
    stickyNav,
    mobileNav,
    heading,
    about,
    skills,
    contact
  },
  methods: {
    toggleStickyNav() {
      let navbar = document.getElementById("stickyNav")
      navbar.classList.toggle('stickynavbar__container--visible')

      let header = document.getElementById("header")
      header.classList.toggle('header--margin-top')
    },
    checkOffset() {
      let offsetY = window.scrollY

      if (offsetY > 93) {
        if (!this.sticky)
          this.toggleStickyNav()

        this.sticky = true
      } else {
        if (this.sticky)
          this.toggleStickyNav()

        this.sticky = false
      }
    }
  },
  beforeMount() {
    window.addEventListener('scroll', this.checkOffset)
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.checkOffset)
  }
}
</script>
