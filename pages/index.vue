<template>
  <div class="HomePage position-absolute w-100 h-100">
    <Loading />
    <div class="HomePage__wrapper position-relative w-100 h-100">
      <Menu v-on:menuToggled="menuToggled = !menuToggled" />
      <HomeButton />
      <div class="title-container">
        <div class="title-wrapper">
          <h1>FFFI MU</h1>
        </div>
      </div>
      <div v-show="!menuToggled" class="HomePage__mouseIcon">
        <ScrollIcon />
      </div>
    </div>
    <div v-show="!menuToggled" class="HomePage__content">
      <h1 class="text-center">Something</h1>
    </div>
    <Footer />
  </div>
</template>

<script>
import Menu from '~/components/menu.vue'
import HomeButton from '~/components/HomeButton.vue'
import Loading from '~/components/Loading.vue'
import Footer from '~/components/Footer.vue'
import ScrollIcon from '~/components/ScrollIcon.vue'

export default {
  components: {
    Menu,
    HomeButton,
    Loading,
    Footer,
    ScrollIcon
  },
  data: () => ({
    menuToggled: false
  })
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=VT323&display=swap');
.title-container {
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: black;
}
.title-wrapper {
  position: relative;
  top: 35%;
}
.title-wrapper > h1 {
  color: white;
  text-align: center;
  font-size: 7rem;
  font-family: 'VT323', monospace;
}
</style>
