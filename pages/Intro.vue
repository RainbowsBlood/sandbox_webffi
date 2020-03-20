<template>
  <div class="">
    <header>
      <Menu :is-light="isLight" />
      <HomeButton :is-light="isLight" />
    </header>
    <h1 class="header__title text-center mx-3 mb-5">
      O festivalu
    </h1>
    <div
      class="intro-text m-auto"
      :class="{ mobile: $device.isMobile, clicked: isClicked }"
      @click="isClicked = true"
    >
      <p>
        Milí fanoušci filmu a studentských snímků, <br />
        <br />
        již 20. ročník Filmového festivalu Fakulty informatiky Masarykovy
        univerzity se bude konat 22. 5. 2020. Vzhledem k současné situaci je
        zatím místo konání nejisté, je možné, že festival bude probíhat online.
        <br />
        <br />
        Místo festivalu je sice nejisté, jisté ale je, že tento ročník festivalu
        bude <b> BEZ CENZURY</b>. Cenzura nás svazuje, odmítá nám ukázat to
        nejzajímavější, diktuje nám co můžeme vidět a co ne. Na festivalu to
        nejzajímavější rozhodně před vámi skrývat nebudeme. S radostí vám
        odhalíme nejlepší studentské filmy z kurzů Produkce audiovizuálního díla
        (PV113) a Základy filmové řeči (PV110) a také externě přihlášené filmy.
        <br />
        <br />
        Filmy budou soutěžit o přízeň odborné poroty, kde prvních pět filmů
        získá finanční ceny. Za svého favorita budou moct hlasovat taky diváci,
        kterých pět největších oblíbenců získá věcné ceny. Odhoďte zábrany,
        vytrhněte se z pout cenzury a nenechte se ujít F*** M*, tedy FFFI MU!
      </p>
    </div>
    <Footer :is-light="isLight" />
  </div>
</template>

<script>
import Menu from '@/components/Menu.vue'
import HomeButton from '@/components/HomeButton.vue'
import Footer from '~/components/Footer.vue'
export default {
  name: 'Intro',
  components: {
    Menu,
    HomeButton,
    Footer
  },
  data: () => ({
    isLight: true,
    isClicked: false
  })
}
</script>

<style lang="css" scoped>
@import '@/assets/lightPage.css';
@import url('@/assets/exo2.css');
@import url('@/assets/exot3.css');
.intro-text {
  width: 60%;
  font-family: 'exo_2regular';
  text-align: justify;
  justify-content: auto;
  font-weight: 350;
  font-size: 1.5rem;
}
.intro-text.mobile {
  font-weight: 300;
  font-size: 1.2rem;
}
.intro-text.clicked {
  font-family: 'Exo 2', sans-serif;
}
</style>
