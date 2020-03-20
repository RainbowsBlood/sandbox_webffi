<template>
  <div class="archive lightPage">
    <div class="archive__header">
      <Menu :is-light="isLight" @menuToggled="isVisible = !isVisible" />
      <HomeButton :is-light="isLight" />
      <div class="header__title text-center mx-3 pt-4 mb-5">
        {{ archive.title }}
      </div>
    </div>

    <div v-show="isVisible" class="archive__years w-75 m-auto">
      <div class="row row-cols-3 d-flex px-auto">
        <div
          v-for="year in archive.years"
          :key="year.year"
          class="col-md-3 mb-5 text-center"
        >
          <h1>
            <a :href="year.link">{{ year.year }}</a>
          </h1>
        </div>
      </div>
    </div>
    <Footer :is-light="isLight" />
  </div>
</template>

<script>
import Menu from '@/components/Menu.vue'
import HomeButton from '@/components/HomeButton.vue'
import Footer from '~/components/Footer.vue'
import Archive from '@/static/archive.json'

export default {
  name: 'Archive',
  components: {
    Menu,
    HomeButton,
    Footer
  },
  data: () => ({
    isVisible: true,
    isLight: true,
    archive: Archive
  })
}
</script>

<style lang="css" scoped>
@import '@/assets/lightPage.css';

.archive__years a {
  text-decoration: none;
  color: #212529;
  opacity: 0.6;
  transition: 0.3s;
}

.archive__years a:hover {
  opacity: 1;
}
</style>
