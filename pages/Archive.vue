<template>
  <div class="archive">
    <div class="bg-lines hidden text-center">
      <svg>
        <line x1="20%" y1="100%" x2="80%" y2="0" />
        <line x1="80%" y1="100%" x2="20%" y2="0" />
      </svg>
    </div>

    <div class="archive__header">
      <Menu v-on:menuToggled="isVisible = !isVisible" />
      <HomeButton />
      <div class="header__title text-center mx-3 pt-4 mb-5">
        Archiv
      </div>
    </div>

    <div v-show="isVisible" class="archive__years w-75 m-auto">
      <div class="row row-cols-3 d-flex px-auto">
        <div
          v-for="year in years.years"
          :key="year.year"
          class="col-md-3 mb-5 text-center"
        >
          <h1>
            <a :href="year.link">{{ year.year }}</a>
          </h1>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Menu from '~/components/Menu.vue'
import HomeButton from '~/components/HomeButton.vue'
import ArchiveYears from '~/archiveYears.json'

export default {
  name: 'Archive',
  components: {
    Menu,
    HomeButton
  },
  data() {
    return {
      isVisible: true,
      years: ArchiveYears
    }
  }
}
</script>

<style lang="css" scoped>
.bg-lines {
  width: 100%;
  height: 100%;
  position: fixed;
  opacity: 0.08;
  top: 0;
  z-index: 0;
  pointer-events: none;
}

.bg-lines svg {
  width: 100%;
  height: 100%;
}

.bg-lines svg line {
  stroke-width: 1;
  stroke: rgb(0, 0, 0);
}

.light-content .bg-lines svg line {
  stroke: rgba(255, 255, 255, 0.137);
}

.archive {
  font-family: 'Anonymous Pro', monospace;
}

.header__title {
  font-weight: 600;
  font-size: 3rem;
}

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
