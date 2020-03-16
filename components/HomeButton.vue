<template>
  <div>
    <button class="HomeButton">
      <div class="HomeButton__logo-link">
        <a href="/#">20</a>
      </div>
    </button>
  </div>
</template>

<script>
export default {
  name: 'HomeButton'
}
</script>

<style lang="css" scoped>
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

.HomeButton__logo-link {
  text-align: center;
  display: block;
  font-family: 'Anonymous Pro', monospace;
  font-weight: 300;
  font-size: 1.5rem;
  margin-left: 0.1rem;
}

.HomeButton__logo-link a {
  text-decoration: none;
  display: block;
  color: #000;
}
</style>
