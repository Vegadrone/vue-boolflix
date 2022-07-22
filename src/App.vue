<template>
  <div id="app">
    <Header  @search="getResultsFromSearchInApi"/>
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
      apiMovieUrl:'https://api.themoviedb.org/3/search/movie',
      apiTvShowsUrl:'https://api.themoviedb.org/3/search/tv',
      apiKey: 'b1f55a1442ac1c7de011ebad1af53cf3',
      filmListFromApi:[],
      tvShowListFromApi:[],
    
    }
  },

  components: {
    Header,
    Main,
  },

  methods: {
    getResultsFromSearchInApi(needle) {
      this.axiosCall()
    },

    axiosCall(url, array){
      axios
        .get(url)
        .then((result) => {
          array = result.data.results;
          console.warn(this.array)
          })
        .catch((error) => {
          console.warn(error)
        })

    }
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
</style>
