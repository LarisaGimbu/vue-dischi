<template>
  <div class="col-10 col-sm-4 col-md-3 col-lg-2 song-box me-4 mb-3 d-flex justify-content-start align-items-center flex-column">
    <img class="pt-3" :src="song.poster" alt="">
    <h5 class="p-2 mb-0 text-center">{{song.title}}</h5>
    <p class="mb-0">{{song.author}}</p>
    <p class="pt-0 year">{{song.year}} </p>
  </div> 
  
  
</template>

<script>
export default {
  name: 'SongsBoxes',
  props:{
    song: Object,
  }
}
</script>

<style lang="scss">
@import '../assets/style/vars.scss';

.song-box{
  width: 100px;
  min-height: 300px;
  background-color: $primary-color;
  color: white;
  &:hover{
    background-color: lighten($primary-color, 10%);
    cursor: pointer;
    img{
      scale: 105%;
    }
    p{
      color: lighten(#808078, 30%);
    }
  }
  img{
    width: 80%;
    object-fit: contain;
  }
  h5{
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