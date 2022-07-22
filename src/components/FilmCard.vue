<template>
  <div class="container">
    <div class="row">
      <div class="col-4">
        <ul>
          <li>{{ singleFilm.title }}</li>
          <li>{{ singleFilm.original_title }}</li>
          <li>{{ singleFilm.original_language }}</li>
          <li>{{ singleFilm.vote_average }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["singleFilm"],
};
</script>

<style>
</style>