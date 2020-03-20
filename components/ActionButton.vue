<template>
  <div class="text-center my-5">
    <a class="actionButton" :href="actionLink">{{ actionText }}</a>
  </div>
</template>

<script>
export default {
  name: 'ActionButton',
  data: () => ({
    actionText: 'Přihlaš film!',
    actionLink: 'https://forms.gle/LD9RVeiquCVPeJYG6'
  })
}
</script>

<style lang="css" scoped>
.actionButton {
  text-decoration: none;
  font-weight: bold;
  color: white;
  font-size: 2rem;
  opacity: 0.8;
  transition: 0.3s;
}

.actionButton:hover {
  opacity: 1;
}
</style>
