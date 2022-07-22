<template>
  <main>
    <FilmCard
      v-for="singleFilm in filmListFromApi"
      :key="singleFilm.id"
      :singleFilm="singleFilm"
    />
    <TvShowCard
      v-for="singleTvShow in tvShowListFromApi"
      :key="singleTvShow.id"
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

  props: ["filmListFromApi", "tvShowListFromApi"],
};
</script>

<style lang="scss">
img {
  width: 2.5rem;
  height: 1.5rem;
}

ul{
  list-style: none;
}
</style>