<template>
  <div class="container">
    <div class="row">
      <div class="col-4">
        <ul>
          <li>{{ singleFilm.title }}</li>
          <li>{{ singleFilm.original_title }}</li>
          <li><img :src="require(`../assets/flags/${singleFilm.original_language}.png`)" alt="language flag"></li>
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

<style lang="scss">
img{
  width: 100px;
  height: 100px;
}
</style>