<template>
  <div class="partners lightPage">
    <div class="partners__header">
      <Menu :is-light="isLight" @menuToggled="isVisible = !isVisible" />
      <HomeButton :is-light="isLight" />
      <div class="header__title text-center mx-3 pt-4">
        {{ partners.title }}
      </div>
    </div>

    <div v-show="isVisible" class="partners__content w-50 m-auto text-center">
      <div v-for="(category, index) in partners.partners" :key="index">
        <h1 class="my-5">
          {{ category.title }}
        </h1>

        <div v-if="category.sponsors">
          <div
            v-for="(partner, index) in category.sponsors"
            :key="index"
            class="row my-3 justify-content-around"
          >
            <div class="col-md-6 col-sm-12 my-3 text-left">
              <h4 class="mb-3">
                {{ partner.company_name }}
              </h4>
              <a :href="partner.company_link">{{ partner.company_link }}</a>
            </div>
            <div class="col-md-3 col-sm-12 text-right">
              <img
                :src="require('../assets/images/' + partner.company_logo)"
                class="content__logo w-75 my-3"
              />
            </div>
          </div>
        </div>

        <div v-else>
          <h6 class="mb-4">
            {{ partners.empty }}
          </h6>
        </div>
      </div>

      <Footer :is-light="isLight" />
    </div>
  </div>
</template>

<script>
import Menu from '@/components/Menu.vue'
import HomeButton from '@/components/HomeButton.vue'
import Footer from '@/components/Footer.vue'

import Partners from '@/static/partners.json'

export default {
  name: 'Partners',
  components: {
    Menu,
    HomeButton,
    Footer
  },
  data: () => ({
    isVisible: true,
    isLight: true,
    partners: Partners
  })
}
</script>

<style lang="css" scoped>
@import '@/assets/lightPage.css';

.partners__content a {
  text-decoration: none;
  color: black;
  font-weight: bold;
  opacity: 0.7;
  transition: 0.3s;
}

.partners__content a:hover {
  opacity: 1;
  text-decoration: none;
  font-weight: bolder;
}

.content__logo {
  width: 30%;
  filter: gray;
  -webkit-filter: grayscale(1);
  transition: all 0.3s ease-in-out;
}

.content__logo:hover {
  filter: none;
  -webkit-filter: grayscale(0);
}
</style>
