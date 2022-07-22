<template>
  <div class="container">
    <div class="row">
      <div class="col-4">
        <ul>
          <li>{{ singleFilm.title }}</li>
          <li>{{ singleFilm.original_title }}</li>
          <li>
            <img
              v-if="languages.includes(singleFilm.original_language)"
              :src="
                require(`../assets/flags/${singleFilm.original_language}.png`)
              "
              alt="language flag"
            />
            <img v-else :src="require(`../assets/flags/rsw.png`)" alt="">
          </li>
          <li>{{ singleFilm.vote_average }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      languages: [
        "de",
        "el",
        "en",
        "es",
        "fr",
        "hi",
        "it",
        "ja",
        "ko",
        "pt",
        "ru",
        "us",
        "zh",
      ],
    };
  },

  props: ["singleFilm"],
};
</script>

<style lang="scss">
</style>