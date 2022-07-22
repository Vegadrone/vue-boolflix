<template>
  <div class="container">
    <div class="row">
      <div class="col-4">
        <ul>
          <li>
            <img
              :src="`${imgBaseUrl}w342${singleTvShow.poster_path}`"
              alt="poster"
            />
          </li>
          <li>{{ singleTvShow.name }}</li>
          <li>{{ singleTvShow.original_name }}</li>
          <li>
            <img
              class="language"
              v-if="supportedLanguages.includes(singleTvShow.original_language)"
              :src="
                require(`../assets/flags/${singleTvShow.original_language}.png`)
              "
              alt="language flag"
            />
            <img class="language"
              v-else
              :src="require(`../assets/flags/rsw.png`)"
              alt="rest-of-the-world"
            />
          </li>
          <li>{{ singleTvShow.vote_average }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      supportedLanguages: [
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

      imgBaseUrl: "https://image.tmdb.org/t/p/",
    };
  },

  props: ["singleTvShow"],

  methods: {},
};
</script>

<style lang="scss">

</style>