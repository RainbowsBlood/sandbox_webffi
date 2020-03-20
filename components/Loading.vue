<template>
  <div>
    <transition name="slide">
      <div v-if="this.i < 100" class="hero">
        <div class="hero-center">
          <transition name="fade" mode="in-out" appear>
            <div>
              <h1>{{ frandom }}</h1>
              <transition name="fade" mode="out-in" appear>
                <footer v-if="this.i > 20">
                  Designed by LEMMA
                </footer>
              </transition>
            </div>
          </transition>
        </div>
      </div>
    </transition>
  </div>
</template>
<script>
export default {
  name: 'Loading',
  data() {
    return {
      frandom: '',
      range: 100,
      i: 0
    }
  },
  mounted() {
    this.generate()
  },
  methods: {
    rndStr(len) {
      let text = ''
      const chars = '$\\/*@#+-!©_¬~?'

      for (let i = 0; i < len; i++) {
        text += chars.charAt(Math.floor(Math.random() * chars.length))
      }

      return text
    },
    generate() {
      setInterval(() => {
        if (this.i < this.range) {
          if (this.i < 50) {
            this.frandom = 'F' + this.rndStr(3) + ' M' + this.rndStr(1)
          } else if (this.i < 52) {
            this.frandom = 'FUCK ME'
          } else if (this.i < 70) {
            this.frandom = 'F*' + this.rndStr(2) + ' M' + this.rndStr(1)
          } else if (this.i < 80) {
            this.frandom = 'F**' + this.rndStr(1) + ' M' + this.rndStr(1)
          } else if (this.i < 90) {
            this.frandom = 'F***' + ' M' + this.rndStr(1)
          } else if (this.i < 95) {
            this.frandom = 'F***' + ' M*'
          }
          this.i += 1
        } else {
          this.frandom = 'FFFI MU'
          clearInterval(this.generate)
        }
      }, 30)
    }
  }
}
</script>
<style lang="css" scoped>
@import url('@/assets/vt323.css');
@import url('@/assets/exo2.css');
html {
  overflow: hidden;
}
.hero {
  position: fixed;
  width: 100vw;
  height: 100vh;
  z-index: 100;
  background-color: #000;
}

.hero-center {
  position: relative;
  width: 100%;
  top: 35%;
  z-index: 100;
  left: 0;
}
h1 {
  font-family: 'VT323', monospace;
  color: #fff;
  font-size: 7rem;
  text-align: center;
  z-index: 100;
  opacity: 1;
}
footer {
  text-align: center;
  color: #fff;
  font-family: 'Exo 2', sans-serif;
  font-size: 1rem;
  position: relative;
  bottom: 0px;
  z-index: 100;
}
.slide-enter-active {
  transition: all 0.3s ease;
}
.slide-leave-active {
  transition: all 0.6s ease-in-out;
}
.slide-enter, .slide-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateY(-100%);
  filter: blur(2px);
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
