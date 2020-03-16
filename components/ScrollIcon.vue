<template>
  <div class="mousey">
    <div class="scroller"></div>
  </div>
</template>

<script>
export default {
  name: 'ScrollIcon'
}
</script>

<style lang="css" scoped>
.mousey {
  margin-left: -17px;
  position: absolute;
  left: 50%;
  bottom: 12rem;
  width: 3px;
  padding: 10px 15px;
  height: 35px;
  border: 2px solid #fff;
  border-radius: 25px;
  opacity: 0.75;
  box-sizing: content-box;
  transition: transform 0.4s;
}
.mousey:hover {
  transform: translateY(1rem);
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
</style>
