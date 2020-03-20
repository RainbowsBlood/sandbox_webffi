<template>
  <div class="align">
    <div class="contact-container">
      <div class="contact-wrapper">
        <h1>KONTAKT</h1>
        <p>
          V případě zájmu o bližší informace <br>
          nás můžete kontaktovat:<br>
          <a href="http://www.fi.muni.cz/usr/sojka/">
            doc. RNDr. Petr Sojka, Ph.D.</a
          ><br />
          <a href="tel:+420549 496 966">tel.: 549 496 966</a><br>
          <a href="mailto:sojka@fi.muni.cz">sojka@fi.muni.cz</a>
        </p>
      </div>
      <div class="place-wrapper">
        <h1>MÍSTO KONÁNÍ</h1>
        <p>
          <b>Fakulta informatiky <br>Masarykovy univerzity</b> <br>
          Botanická 68a <br>
          602 00 Brno <br>
          Česká republika
        </p>
        <p>
          <b>Univerzitní kino Scala </b> <br>
          Moravské náměstí 3/127<br>
          602 00 Brno<br>
          Česká republika
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Contact'
}
</script>

<style lang="css" scoped>
.align {
  text-align: center;
  margin-right: auto;
  margin-left: auto;
  display: table;
}
.contact-container {
  margin-top: 3rem;
  position: relative;
  text-align: center;
  width: 100%;

  color: white;
}
.contact-wrapper {
  margin: 20px;
  float: left;
}
.contact-wrapper > p {
  text-align: left;
  margin: 10px;
}
.contact-wrapper > p > a {
  font-weight: 500;
  text-align: left;
  color: white;
  text-decoration: none;
}
.contact-wrapper > p > a:hover {
  font-weight: 700;
}
.place-wrapper {
  margin: 20px;
  display: block;
  float: right;
}
.place-wrapper > p {
  text-align: left;
  line-height: 20px;
  margin: 10px;
  display: block;
  float: left;
}
</style>
