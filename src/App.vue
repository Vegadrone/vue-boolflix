<template>
  <div id="app">
    <Header  @search="getFilmFromSearchInApi"/>
    <Main :filmListFromApi="filmListFromApi"
          />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import axios from "axios";

export default {
  name: "App",

  data: function(){
    return{
      filmListFromApi:[],
    
    }
  },

  components: {
    Header,
    Main,
  },

  methods: {
    getFilmFromSearchInApi(needle) {
      axios
        .get(`https://api.themoviedb.org/3/search/movie?api_key=b1f55a1442ac1c7de011ebad1af53cf3&query=${needle}`
        )
        .then((result) => {
          this.filmListFromApi = result.data.results;
          console.warn(this.filmListFromApi)
          })
        .catch((error) => {
          console.warn(error)
        })
    },
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
</style>
