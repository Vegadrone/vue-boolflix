<template>
  <main>
    <div class="container">
      <div class="row">
        <div class="col-12">
          <FilmCard
            class="mt-4"
            v-for="singleFilm in filmListFromApi"
            :key="singleFilm.id"
            :singleFilm="singleFilm"
          />
          <TvShowCard
            class="mt-4"
            v-for="singleTvShow in tvShowListFromApi"
            :key="singleTvShow.id"
            :singleTvShow="singleTvShow"
          />
        </div>
      </div>
    </div>
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
main {
  background-color: #1b1b1b;
}

ul {
  list-style: none;
}
</style>