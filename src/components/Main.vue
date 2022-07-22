<template>
  <main>
    <FilmCard
      v-for="(singleFilmOrShow, index) in showsAndMovies"
      :key="index"
      :singleFilmOrShow="singleFilmOrShow"
    />
    <TvShowCard/>
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

  data:function(){
    return{
      showsAndMovies:[],
    }
  },

  props: {
    propA:"filmListFromApi", 
    propB:"tvShowListFromApi",
  },

  methods:{
    mergeShowsandFilms(){
      this.showsAndMovies = this.props.propA + this.props.propB;
    }
  },

  created(){
    mergeShowsandFilms();
  }
};
</script>

<style>
</style>