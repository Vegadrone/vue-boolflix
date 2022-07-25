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
      apiUrl: "https://api.themoviedb.org/3/search/",
      apiKey: "b1f55a1442ac1c7de011ebad1af53cf3",
      filmListFromApi: [],
      tvShowListFromApi: [],
    };
  },

  components: {
    Header,
    Main,
  },

  methods: {
    getResultsFromSearchInApi(apiParams) {
      axios
        .get(this.apiUrl +  'movie', apiParams)
        .then((result) => {
          this.filmListFromApi = result.data.results;
          console.warn(this.filmListFromApi);
        })
        .catch((error) => {
          console.warn(error);
        });

      axios
        .get(this.apiUrl +  'tv', apiParams)
        .then((result) => {
          this.tvShowListFromApi = result.data.results;
          console.warn(this.tvShowListFromApi);
        })
        .catch((error) => {
          console.warn(error);
        });
    },

    apiSearch: function(needle){
      const apiParams = {
        params:{
          api_key: this.apiKey,
          language:'it-IT',
          query: needle,
        }
      }
      this.getResultsFromSearchInApi(apiParams);
    }
    
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";

</style>
