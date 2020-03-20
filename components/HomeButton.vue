<template>
  <div>
    <button
      class="HomeButton"
      :class="{ light: isLight, mobile: $device.isMobile, hoverscope: hover }"
      @mouseover="hover = true"
    >
      <div v-if="!hover" class="HomeButton__logo-link">
        <a :class="{ light: isLight }" href="/">20</a>
      </div>
    </button>
  </div>
</template>

<script>
export default {
  name: 'HomeButton',
  props: ['isLight'],
  data: () => ({
    hover: false
  })
}
</script>

<style lang="css" scoped>
@import url('@/assets/exo2.css');
.HomeButton {
  width: 3rem;
  height: 3rem;
  border-radius: 32px;
  box-sizing: border-box;
  background-color: #fff;
  position: fixed;
  left: 3rem;
  top: 3rem;
  margin-top: -20px;
  margin-right: -20px;
  cursor: pointer;
  z-index: 2;
  border-style: none;
}

.HomeButton:focus {
  outline: none;
}
.HomeButton.mobile {
  left: 1rem;
}
.HomeButton.light {
  background-color: black;
}
.HomeButton__logo-link {
  text-align: center;
  display: block;
  font-family: 'Exo 2', sans-serif;
  font-weight: 300;
  font-size: 1.5rem;
}

.HomeButton__logo-link a {
  text-decoration: none;
  display: block;
  color: #000;
}
.HomeButton__logo-link a.light {
  color: white;
}
.hoverscope {
  z-index: 10;
  background-image: url('../assets/images/monoscope.gif');
  background-position: center; /* Center the image */
  background-repeat: no-repeat; /* Do not repeat the image */
  background-size: cover;
  animation-name: fade;
  animation-duration: 2s;
}
@keyframes fade {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
</style>
