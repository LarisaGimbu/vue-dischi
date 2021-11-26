<template>
  <header>
    <div class="logo">
      <i class="fab fa-spotify p-2"></i>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="scss">
@import '../assets/style/vars.scss';

header{
  background-color: $primary-color;
  .fa-spotify{
    font-size: 2rem;
    color: $logo-color;
  }
}

</style>