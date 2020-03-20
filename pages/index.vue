<template>
  <div>
    <Loading />
    <div>
      <header>
        <Menu />
        <HomeButton />
      </header>
      <section id="title">
        <div class="title-container">
          <transition name="fade">
            <div v-show="titleClicked" class="photo" />
          </transition>
          <div
            class="title-wrapper"
            @click="titleClicked = true"
            @mouseover="titleHover = true"
          >
            <h1 v-if="titleHover">
              FFFI MU
            </h1>
            <h1 v-else>
              F*** M*
            </h1>
            <transition name="fade-slide">
              <div v-if="titleHover" class="sub-title">
                <p>
                  22. 5. 2020 <br />
                  19:00
                </p>
              </div>
            </transition>
          </div>
        </div>
      </section>
      <div>
        <a v-smooth-scroll="{ duration: 1000, offset: -150 }" href="#trailer"
          ><ScrollIcon
        /></a>
      </div>
    </div>

    <div>
      <section id="trailer">
        <div class="content__trailer">
          <Trailer />
        </div>
      </section>
      <PartnersTable />
      <Contact />
      <Footer />
    </div>
  </div>
</template>

<script>
import Vue from 'vue'
import vueSmoothScroll from 'vue-smooth-scroll'
Vue.use(vueSmoothScroll)

import Menu from '~/components/Menu.vue'
import HomeButton from '~/components/HomeButton.vue'
import Loading from '~/components/Loading.vue'
import Footer from '~/components/Footer.vue'
import ScrollIcon from '~/components/ScrollIcon.vue'
import Trailer from '~/components/Trailer.vue'
import Contact from '~/components/Contact.vue'
import PartnersTable from '~/components/PartnersTable.vue'

export default {
  components: {
    Menu,
    HomeButton,
    Loading,
    Footer,
    ScrollIcon,
    Trailer,
    Contact,
    PartnersTable
  },
  data: () => ({
    menuToggled: false,
    titleHover: false,
    titleClicked: false
  })
}
</script>

<style>
@import url('@/assets/vt323.css');
@import url('@/assets/exo2.css');
body {
  background: #000;
  font-family: 'Exo 2', sans-serif;
}

.title-container {
  position: relative;
  width: 100%;
  height: 100vh;
  background-color: black;
}
.photo {
  opacity: 0.25;
  position: absolute;
  width: 100%;
  height: 100vh;
  background-image: url('../assets/images/bg.png');
  background-position: center; /* Center the image */
  background-repeat: no-repeat; /* Do not repeat the image */
  background-size: cover;

  filter: blur(2px);
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
  transition: all 0.4s;
}
.sub-title {
  color: #999;
  text-align: center;
  font-size: 3rem;
  font-family: 'VT323', monospace;
  line-height: 2.5rem;
  pointer-events: none;
}
.content__trailer {
  align-content: center;
  margin-top: 20vh;
}
.fade-slide-enter-active,
.fade-slide-leave-active {
  -webkit-transition: all 0.2s ease-in-out 0.2s;
  transition: all 0.2s ease-in-out 0.2s;
}

.fade-slide-enter, .fade-slide-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
  transform: translateY(-60px);
}
.fade-enter-active,
.fade-leave-active {
  -webkit-transition: opacity 0.2s ease-in-out 0.2s;
  transition: opacity 0.2s ease-in-out 0.2s;
}

.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
