<template>
  <header class="d-flex justify-content-between align-items-center">
    <div class="logo">
      <i class="fab fa-spotify p-2"></i>
    </div>

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
  </header>
</template>

<script>
export default {
  name: 'Header',
  data(){
    return{
      genreToSearch: '',
    }
  },
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

  select.form-select{
    width: 210px;
    background-color: lighten($primary-color, 10%);
    border: 2px solid $main-color;
    color: white;
  }
}

</style>