<template>
  <div class="footer-container">
    <footer>
      <div class="socials" :class="{ light: isLight }">
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
  name: 'Footer',
  props: ['isLight']
}
</script>

<style lang="css" scoped>
@import url('@/assets/exo2.css');
.footer-container {
  font-family: 'Exo 2', sans-serif;
  padding: 20px;
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
.socials.light > a {
  color: black;
}
</style>
