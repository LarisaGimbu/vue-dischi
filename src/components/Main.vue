<template>
  <main>
    <div class="container">
      <div 
      v-if="loading"
      class="row justify-content-center pt-5">
        <SongsBoxes 
        v-for="(song, index) in songs"
        :key="index"
        :song="song" />
      </div>
      <div v-else>
        <Loading />
      </div>
      
    </div>
  </main>
</template>

<script>
import SongsBoxes from './SongsBoxes.vue';
import Loading from './Loading.vue';
import axios from 'axios';

export default {
  name: 'Main',
  components:{
    SongsBoxes,
    Loading
  },
  data(){
    return{
      songs: [],
      loading: false,
    }
  },
  methods:{
    getApi(){
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then( r =>{
          this.songs = r.data.response;
          this.loading = true;
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