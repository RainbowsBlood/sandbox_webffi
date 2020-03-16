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
      <Footer />
    </div>
    <div v-show="!menuToggled" class="HomePage__content position-relative">
      <h1 class="text-center">Something</h1>
    </div>
  </div>
</template>

<script>
import Menu from '~/components/menu.vue'
import HomeButton from '~/components/homebutton.vue'
import Loading from '~/components/loading.vue'
import Footer from '~/components/footer.vue'
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
<link href="https://fonts.googleapis.com/css?family=VT323&display=swap" rel="stylesheet">
<style>
@import url('https://fonts.googleapis.com/css?family=VT323&display=swap');
.title-container {
  position: fixed;
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
