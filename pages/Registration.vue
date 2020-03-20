<template>
  <div class="registration lightPage">
    <Menu :is-light="isLight" @menuToggled="isVisible = !isVisible" />
    <HomeButton :is-light="isLight" />
    <div class="registration__header">
      <div class="header__title text-center mx-3 pt-4 mb-5 mw-75">
        {{ registration.main_title }}
      </div>
    </div>

    <div
      v-show="isVisible"
      class="registration__content w-50 m-auto text-center"
    >
      <div class="content__intro">
        <h3 class="mb-4">
          {{ registration.intro_title }}
        </h3>
        <span v-for="(string, index) in registration.intro" :key="index">
          <span v-html="string" />
        </span>
      </div>
      <div class="content__rules">
        <h3 class="my-4">
          {{ registration.rules_title }}
        </h3>
        <span v-for="(string, index) in registration.rules" :key="index">
          <span v-html="string" />
        </span>
      </div>
    </div>
    <Footer :is-light="isLight" />
  </div>
</template>

<script>
import Menu from '@/components/Menu.vue'
import HomeButton from '@/components/HomeButton.vue'
import Footer from '@/components/Footer.vue'
import Registration from '@/static/registration.json'

export default {
  name: 'Registration',
  components: {
    Menu,
    HomeButton,
    Footer
  },
  data: () => ({
    isVisible: true,
    isLight: true,
    registration: Registration
  })
}
</script>

<style lang="css" scoped>
@import '@/assets/lightPage.css';

.registration__content >>> a {
  text-decoration: none;
  color: black;
  font-weight: bold;
  opacity: 0.7;
  transition: 0.3s;
}

.registration__content >>> a:hover {
  opacity: 1;
  text-decoration: none;
  font-weight: bolder;
}
</style>
