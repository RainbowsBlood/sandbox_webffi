<template>
  <div class="footer-container">
    <footer>
      <div class="socials">
        <a href="https://www.facebook.com/festival.fi.muni.cz">
          <font-awesome-icon :icon="['fab', 'facebook-square']" size="lg"
        /></a>
        <a href="https://www.youtube.com/user/fffilemma"
          ><font-awesome-icon :icon="['fab', 'youtube-square']" size="lg"
        /></a>
        <a href="https://www.instagram.com/fffimu/"
          ><font-awesome-icon :icon="['fab', 'instagram']" size="lg"
        /></a>
      </div>
      <p class="copyright">
        2020 ©
        <a target="_blank" href="http://www.fi.muni.cz/">Fakulta Informatiky</a
        >. Designed by
        <a target="_blank" href="http://lemma.fi.muni.cz/">LEMMA</a>.
      </p>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style lang="css" scoped>
.footer-container {
  position: absolute;
  padding: 70px 20px 50px 20px;
  width: 100%;
  height: 200px;
  z-index: 1;
  bottom: 0;
  box-sizing: border-box;
  text-align: center;
}
.copyright {
  font-size: 12px;
  color: #999;
  width: 100%;
  margin-top: 10px;
  margin-bottom: 10px;
  line-height: 28px;
}
.copyright > a {
  color: #999;
  text-decoration: none;
}
.socials > a {
  color: white;
  margin: 0.5rem;
}
</style>
