<template>
  <main>
    <div class="container-fluid">
      <div class="row">
        <div class="col-12 d-flex flex-wrap justify-content-between">
          <FilmCard
            class="mt-4 film-card"
            v-for="singleFilm in filmListFromApi"
            :key="singleFilm.id"
            :singleFilm="singleFilm"
          />
          <TvShowCard
            class="mt-4  tv-show-card"
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