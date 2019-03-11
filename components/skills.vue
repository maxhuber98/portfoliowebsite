<template>
  <section id="skills" class="skills">
    <div class="skills__wrapper">
      <h1 class="skills__title">Skills</h1>

      <div class="skills__container">
        <div class="skills__row">
          <h1 class="skills__name">HTML</h1>
          <div class="skills__bar-placeholder">
            <div class="skills__bar" style="width:85%;">
              <span class="skills__bar-inner" :class="{ 'skills__bar-inner--visible': visible}"></span>
            </div>
          </div>
        </div>

        <div class="skills__row">
          <h1 class="skills__name">C#</h1>
          <div class="skills__bar-placeholder">
            <div class="skills__bar" style="width:80%;">
              <span class="skills__bar-inner" :class="{ 'skills__bar-inner--visible': visible}"></span>
            </div>
          </div>
        </div>

        <div class="skills__row">
          <h1 class="skills__name">JavaScript</h1>
          <div class="skills__bar-placeholder">
            <div class="skills__bar" style="width:75%;">
              <span class="skills__bar-inner" :class="{ 'skills__bar-inner--visible': visible}"></span>
            </div>
          </div>
        </div>

        <div class="skills__row">
          <h1 class="skills__name">CSS</h1>
          <div class="skills__bar-placeholder">
            <div class="skills__bar" style="width:70%;">
              <span class="skills__bar-inner" :class="{ 'skills__bar-inner--visible': visible}"></span>
            </div>
          </div>
        </div>

        <div class="skills__row">
          <h1 class="skills__name">PHP</h1>
          <div class="skills__bar-placeholder">
            <div class="skills__bar" style="width:65%;">
              <span class="skills__bar-inner" :class="{ 'skills__bar-inner--visible': visible}"></span>
            </div>
          </div>
        </div>
      </div>
    </div>
    
  </section>
</template>

<script>
export default {
  data() {
    return {
      visible: false
    }
  },
  methods: {
    handeScroll() {
      const skillsSection = document.getElementsByClassName('skills')[0]
      const offsetSkillsSection = skillsSection.scrollHeight
      const scrollHeight = window.scrollY

      if (scrollHeight >= offsetSkillsSection) {
        this.visible = true
      }
    },
  },
  beforeMount() {
    window.addEventListener('scroll', this.handeScroll)
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handeScroll)
  }
}
</script>