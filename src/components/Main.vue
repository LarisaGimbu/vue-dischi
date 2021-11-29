<template>
  <main>
    <Select @sendSearch='performSearch'/>
    <div class="container">
      <div 
      v-if="loading"
      class="row justify-content-center pt-5">
        <SongsBoxes 
        v-for="(song, index) in filteredSongs"
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
import Select from './Select.vue';
import axios from 'axios';

export default {
  name: 'Main',
  components:{
    SongsBoxes,
    Loading,
    Select
  },
  data(){
    return{
      songs: [],
      loading: false,
      textToSearch:''
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
    },
    performSearch(text){
      this.textToSearch = text
      console.log(this.textToSearch);

    }
  },
  computed:{
    filteredSongs(){
      if(this.textToSearch === ''){
        return this.songs;
      }
      return this.songs.filter(song =>{
        return song.genre.includes(this.textToSearch);
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
  position: relative;
  width: 100%;
  min-height: calc(100vh - 48px);
  background-color: $main-color;
}

</style>