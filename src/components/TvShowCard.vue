<template>
  <div class="container">
    <div class="row">
      <div class="col-4">
        <ul>
          <li>{{ singleTvShow.name }}</li>
          <li>{{ singleTvShow.original_name }}</li>
          <li><img :src="require(`../assets/flags/${singleTvShow.original_language}.png`)" alt="language flag"></li>
          <li>{{ singleTvShow.vote_average }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["singleTvShow"],

  methods:{

  }
};
</script>

<style lang="scss">
    img{
        width: 100px;
        height: 100px;
    }
</style>