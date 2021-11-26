<template>
  <main>
    <div class="container">
      <SongsBoxes />
    </div>
  </main>
</template>

<script>
import SongsBoxes from './SongsBoxes.vue'

export default {
  name: 'Main',
  components:{
    SongsBoxes,
  }
}
</script>

<style lang="scss">
@import '../assets/style/vars.scss';

main{
  width: 100%;
  min-height: calc(100vh - 48px);
  background-color: #1E2D3B;
}

</style>