<template>
  <div class="nav-container">
    <div v-if="$device.isDesktop" class="mousey">
      <div class="scroller" />
    </div>
    <font-awesome-icon
      v-if="$device.isMobile || $device.isTablet"
      class="angle"
      :icon="['fas', 'angle-down']"
      size="6x"
      color="white"
    />
  </div>
</template>

<script>
export default {
  name: 'ScrollIcon'
}
</script>

<style lang="css" scoped>
.nav-container {
  position: relative;
  text-align: center;
  opacity: 0.5;
  bottom: 16rem;
  transition: transform 0.4s ease-in-out;
}
.angle {
  margin-left: 0.25rem;
  margin-top: 6rem;
  animation-name: move;
  animation-duration: 2s;
  animation-timing-function: none;
  animation-iteration-count: infinite;
  color: white;
}
.mousey {
  position: relative;
  left: 50%;
  box-sizing: content-box;
  margin-left: -18px;
  width: 3px;
  padding: 10px 16px;
  height: 35px;
  border: 2px solid #fff;
  border-radius: 25px;
  margin-top: 8rem;
}
.nav-container:hover {
  transform: translateY(1rem);
  opacity: 1;
}

.scroller {
  width: 3px;
  height: 10px;
  border-radius: 25%;
  background-color: #fff;
  animation-name: scroll;
  animation-duration: 2.2s;
  animation-timing-function: cubic-bezier(0.15, 0.41, 0.69, 0.94);
  animation-iteration-count: infinite;
}
@keyframes scroll {
  0% {
    opacity: 0;
  }
  10% {
    transform: translateY(0);
    opacity: 1;
  }
  100% {
    transform: translateY(1rem);
    opacity: 0;
  }
}
@keyframes move {
  10% {
    transform: translateY(0);
  }
  60% {
    transform: translateY(1.5rem);
  }
  80% {
    transform: translateY(-0.05rem);
  }
}
</style>
