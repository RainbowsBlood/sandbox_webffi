<template>
  <div>
    <div class="partnersTable__container w-50 mx-auto">
      <div
        v-for="(row, index) in partners"
        :key="index"
        class="row table__row m-0 w-100 h-100"
      >
        <div
          v-for="(partner, index) in row"
          :key="index"
          class="table__item col-md-3 col-sm-2"
        >
          <div class="text-center py-4">
            <img
              :src="require('../assets/images/' + partner + '.png')"
              class="table__logo"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PartnersTable',
  data: () => ({
    partners: [
      ['abra', 'solarwinds', 'brno', '24i'],
      ['kentico', 'muni', 'redhat_white', 'sportbalkan_white']
    ]
  })
}
</script>

<style lang="css" scoped>
.partnersTable__container {
  margin-top: 5rem;
  background-color: rgba(12, 12, 12, 0.664);
  -webkit-box-shadow: 3px 22px 70px -17px rgba(28, 28, 28, 1);
  -moz-box-shadow: 3px 22px 70px -17px rgba(28, 28, 28, 1);
  box-shadow: 3px 22px 70px -17px rgba(28, 28, 28, 1);
}

.table__item {
  border: solid 0.5px rgb(31, 31, 31);
}

.table__row {
  min-height: 5rem;
}

.table__logo {
  display: inline-block;
  max-height: 2rem;
  max-width: 6.5rem;
  filter: gray;
  -webkit-filter: grayscale(0.75);
  transition: all 0.3s ease-in-out;
}

.table__logo:hover {
  filter: none;
  -webkit-filter: grayscale(0);
}
</style>
