<template>
  <div id="app">
    <Header @search="getResultsFromSearchInApi" />
    <Main
      :filmListFromApi="filmListFromApi"
      :tvShowListFromApi="tvShowListFromApi"
    />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import axios from "axios";

export default {
  name: "App",

  data: function () {
    return {
      apiMovieUrl: "https://api.themoviedb.org/3/search/movie",
      apiTvShowsUrl: "https://api.themoviedb.org/3/search/tv",
      apiKey: "b1f55a1442ac1c7de011ebad1af53cf3",
      filmListFromApi: [],
      tvShowListFromApi: [],
      languageList:[],
    };
  },

  components: {
    Header,
    Main,
  },

  methods: {
    getResultsFromSearchInApi(needle) {
      axios
        .get(`${this.apiMovieUrl}?api_key=${this.apiKey}&query=${needle}`)
        .then((result) => {
          this.filmListFromApi = result.data.results;
          console.warn(this.filmListFromApi);
        })
        .catch((error) => {
          console.warn(error);
        });

      axios
        .get(`${this.apiTvShowsUrl}?api_key=${this.apiKey}&query=${needle}`)
        .then((result) => {
          this.tvShowListFromApi = result.data.results;
          console.warn(this.tvShowListFromApi);
        })
        .catch((error) => {
          console.warn(error);
        });
    },

    
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";

#app{
  background-color: #1b1b1b;
}


</style>
