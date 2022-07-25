<template>
  <main>
    <div class="container-fluid">
      <div class="row">
        <h1 class="text-light fw-bold text-center mt-3">Films</h1>
        <div class="col-12 d-flex flex-wrap justify-content-between">
          <FilmCard
            class="mt-4 film-card"
            v-for="singleFilm in filmListFromApi"
            :key="singleFilm.id"
            :singleFilm="singleFilm"
          />
        </div>
      </div>
      <hr class="text-light mt-5">
      <div class="row">
        <h1 class="text-light fw-bold text-center mt-3">Series</h1>
        <div class="col-12 d-flex flex-wrap justify-content-between">
          <TvShowCard
            class="mt-4 tv-show-card"
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
ul {
  list-style: none;
}

main {
  background-color: #1b1b1b;
}

.film-card,
.tv-show-card {
  width: calc((100% / 3) - 3rem);
  padding: 2rem;
}


</style>