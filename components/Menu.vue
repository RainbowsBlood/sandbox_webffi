<template>
  <div>
    <button class="menu-button" @click="toggleMenu()">
      <div class="menu-burger" :class="{ open: !ishidden, light: islight }">
        <span :class="{ light: islight }"></span>
        <span :class="{ light: islight }"></span>
      </div>
    </button>
    <transition name="fade">
      <div
        v-show="!ishidden"
        class="menu"
        :class="{ light: islight, hidden: ishidden }"
      >
        <div class="menu-container">
          <ul style="padding-inline-start: 0">
            <li v-for="item in items" :key="item.id">
              <a
                class="line"
                :class="{ hidden: ishidden, light: islight }"
                :href="item.href"
              >
                {{ item.title }}</a
              >
            </li>
          </ul>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'Menu',
  data() {
    return {
      islight: false,
      ishidden: true,
      items: [
        {
          title: 'Domů',
          href: '/#',
          active: true
        },
        {
          title: 'Archiv',
          href: '/archive',
          active: false
        },
        {
          title: 'Přihlaš film',
          href:
            'https://docs.google.com/forms/u/2/d/e/1FAIpQLSe45Lk9wwninlk183Z3k2Nx_7tim7vwwWkL0B2RFRZGLRMZ_A/viewform?usp=send_form',
          active: false
        }
      ]
    }
  },
  methods: {
    toggleMenu() {
      this.ishidden = !this.ishidden
    }
  }
}
</script>

<style lang="css" scoped>
.menu-button {
  width: 3rem;
  height: 3rem;
  border-radius: 32px;
  box-sizing: border-box;
  background-color: #fff;
  position: fixed;
  right: 3rem;
  top: 3rem;
  margin-top: -20px;
  margin-left: -20px;
  cursor: pointer;
  z-index: 3;
  border-style: none;
}

.menu-button:focus {
  outline: none;
}

.menu-button.light {
  background-color: #000;
}

.menu-burger {
  width: 14px;
  height: 22px;
  position: relative;
  margin: 0 auto;
  pointer-events: none;
  -webkit-transition: background-color 0.2s ease-in-out;
  transition: background-color 0.2s ease-in-out;
}

.menu-burger span {
  display: block;
  position: absolute;
  height: 0.05rem;
  width: 100%;
  background: #000 !important;
  opacity: 1;
  right: 0;
  -webkit-transform: rotate(0deg);
  -moz-transform: rotate(0deg);
  -o-transform: rotate(0deg);
  transform: rotate(0deg);
  -webkit-transition: 0.2s ease-in-out;
  -moz-transition: 0.2s ease-in-out;
  -o-transition: 0.2s ease-in-out;
  transition: 0.2s ease-in-out;
}
span.light {
  backround: #fff;
}
.menu-burger span:nth-child(1) {
  top: 8px;
}
.menu-burger span:nth-child(2) {
  top: 14px;
}
.menu-burger.open span:nth-child(1) {
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -o-transform: rotate(45deg);
  transform: rotate(45deg);
  top: 10px;
}

.menu-burger.open span:nth-child(2) {
  -webkit-transform: rotate(-45deg);
  -moz-transform: rotate(-45deg);
  -o-transform: rotate(-45deg);
  transform: rotate(-45deg);
  top: 10px;
}

.menu {
  position: fixed;
  width: 100%;
  height: 100%;
  background: #000 !important;
  background-image: none !important;
  box-sizing: border-box;
  z-index: 2;
}

.menu-container {
  width: 100%;
  position: absolute;
  top: 30%;
  left: 0;
  text-align: center;
}
.hidden {
  opacity: 0;
}
.line {
  display: block;
  padding: 0.5rem;
  cursor: pointer;
  color: #fff;
  line-height: 64px;
  font-size: 3.5rem;
  font-weight: 600;
  position: relative;
  font-family: 'Anonymous Pro', monospace;
  text-decoration: none;
}
.line.light {
  color: #000;
}
li {
  list-style-type: none;
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
