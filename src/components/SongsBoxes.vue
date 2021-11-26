<template>
  <div class="row justify-content-center pt-5">
    <div class="col-2 song-box me-4 mb-3 d-flex justify-content-start align-items-center flex-column">
      <img class="pt-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
      <h3 class="p-2 mb-0">New Jersey</h3>
      <p class="mb-0">Bon Jovi</p>
      <p class="pt-0 year">1988</p>
    </div>       
  </div>
  
</template>

<script>
export default {
  name: 'SongsBoxes'
}
</script>

<style lang="scss">
@import '../assets/style/vars.scss';

.song-box{
  width: 100px;
  height: 300px;
  background-color: $primary-color;
  color: white;
  img{
    width: 90%;
    object-fit: contain;
  }
  h3{
    text-transform: uppercase;
  }
  p{
    color: #808078;
    font-size: 1.2rem;
    &.year{
      font-size: 0.9rem;
    }
  }
}
</style>