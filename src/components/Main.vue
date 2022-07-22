<template>
  <main>
    <FilmCard
      v-for="(singleFilm, index) in filmListFromApi"
      :key="index"
      :singleFilm="singleFilm"
    />
    <TvShowCard
      v-for="(singleTvShow,index) in tvShowListFromApi" 
      :key="index"
      :singleTvShow="singleTvShow"
     />
  </main>
</template>

<script>
import FilmCard from "./FilmCard.vue";
import TvShowCard from "./TvShowCard.vue";

export default {
  components: {
    FilmCard,
    TvShowCard,
  },

  props:[
    'filmListFromApi', 
    'tvShowListFromApi'
  ]
};
</script>

<style>
</style>