<template>
  <header>
    <div class="container">
      <div class="row">
        <div class="col-4 mt-4">
          <form class="d-flex" role="search">
            <input
              class="form-control me-2"
              placeholder="Cerca Film o Serie TV"
              v-model="searchedMovie"
            />
            <button class="btn btn-outline-primary" type="submit" @click.prevent="$emit('search',searchedMovie)">
              Cerca
            </button>
          </form>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data: function(){
    return{
      searchedMovie:'',
    }
  },

  methods:{
    
  }
};
</script>

<style>
</style>
