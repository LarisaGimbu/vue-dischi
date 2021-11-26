<template>
  <main>
    <div class="container">
      <div class="row justify-content-center pt-5">
        <SongsBoxes 
        v-for="(song, index) in songs"
        :key="index"
        :song="song" />
      </div>
      
    </div>
  </main>
</template>

<script>
import SongsBoxes from './SongsBoxes.vue';
import axios from 'axios';

export default {
  name: 'Main',
  components:{
    SongsBoxes,
  },
  data(){
    return{
      songs: []
    }
  },
  methods:{
    getApi(){
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then( r =>{
          this.songs = r.data.response;
        })
        .catch((error) =>{
          console.log(error);
        })
    }
  },
  mounted(){
    this.getApi()
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