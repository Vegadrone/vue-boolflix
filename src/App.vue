<template>
  <div id="app">
    <Header />
    <Main />
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
      apiMovieUrl:"https://api.themoviedb.org/3/search/movie?api_key=b1f55a1442ac1c7de011ebad1af53cf3&query=fantozzi"
    }
  },

  components: {
    Header,
    Main,
  },

  methods: {
    getFilmFromSearch() {
      axios
        .get(
          this.apiMovieUrl
        )
        .then((result) => {
          console.log(result);
        })
        .catch((error) => {
          console.warn(error)
        })
    },
  },

  created(){
    this.getFilmFromSearch();
  }
  
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
</style>
