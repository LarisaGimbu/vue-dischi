<template>
  <div class="col-10 col-sm-4 col-md-3 col-lg-2 song-box me-4 mb-3 d-flex justify-content-start align-items-center flex-column">
    <img class="pt-3" :src="song.poster" alt="">
    <i class="far fa-play-circle"></i>
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
  position: relative;
  width: 100px;
  min-height: 300px;
  background-color: $primary-color;
  color: white;
  transition: all .5s;
  &:hover{
    background-color: lighten($primary-color, 10%);
    cursor: pointer;
    img{
      scale: 105%;
    }
    i{
      display: block;
      text-shadow: 0 3px 2px $primary-color;
    }
    p{
      color: lighten(#808078, 30%);
    }
  }
  img{
    width: 80%;
    object-fit: contain;
  }
  i{
    display: none;
    position: absolute;
    top: 23%;
    left: 43%;
    font-size: 2rem;
    opacity: 0.8;
    &:hover{
      scale: 105%;
    }
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