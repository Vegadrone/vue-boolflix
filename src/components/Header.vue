<template>
  <header>
    <div class="container">
      <div class="row d-flex justify-content-between">
        <div class="col-3">
          <h1 class="text-danger fw-bold text-upercase">Boolflix</h1>
        </div>
        <div class="col-3 mt-2">
          <form class="d-flex" role="search">
            <input
              
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

<style lang="scss">

header{
  background-color: #030303 ;
}

</style>
