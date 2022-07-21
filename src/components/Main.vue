<template>
  <main>
    <FilmCard
      v-for="(singleFilmFromApi, index) in filmListFromApi"
      :key="index"
      :singleFilmFromApi="singleFilmFromApi"
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