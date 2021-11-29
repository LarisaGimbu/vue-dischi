<template>
    <select 
    v-model="genreToSearch"
    @change="$emit('sendSearch',genreToSearch)"
    class="form-select" aria-label="Default select example">
      <option selected>Selezionare un genere</option>
      <option value="Rock">Rock</option>
      <option value="Pop">Pop</option>
      <option value="Jazz">Jazz</option>
      <option value="Metal">Metal</option>
    </select>
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

  select.form-select{
    position: absolute;
    top: -45px;
    right: 5px;
    width: 210px;
    background-color: lighten($primary-color, 10%);
    border: 2px solid $main-color;
    color: white;
  }

</style>