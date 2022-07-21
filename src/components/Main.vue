<template>
  <main>
    <FilmCard
      v-for="singleFilmFromApi in filmListFromApi"
      :key="singleFilmFromApi.id"
      :singlefilmfromApi="singleFilmFromApi"
    />
  </main>
</template>

<script>
import FilmCard from "./FilmCard.vue";

export default {
  components: {
    FilmCard,
  },

  props: ["filmListFromApi"],
};
</script>

<style>
</style>