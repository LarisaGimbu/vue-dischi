<template>
    <div class="select-box d-flex align-items-center">
      <label for="select">Choose a genre:</label>
      <select
      value="select"
      v-model="genreToSearch"
      @change="$emit('sendSearch',genreToSearch)"
      class="form-select" aria-label="Ciao">
        <option value="All">All</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
      </select>
    </div>
</template>

<script>
export default {
  name: 'Select',
  data(){
    return{
      genreToSearch: '',
    }
  },
}
</script>

<style lang='scss'>
@import '../assets/style/vars.scss';
.select-box{
  position: absolute;
    top: -45px;
    right: 5px;
  label{
    color: white;
    padding-right: 5px;
  }
  select.form-select{
    
    width: 100px;
    background-color: lighten($primary-color, 10%);
    border: 2px solid $main-color;
    color: white;
  }
}
</style>