<template>
  <div class="container">
    <div class="row">
      <div class="col-4">
        <ul>
          <li><img :src="`${imgBaseUrl}w342${singleFilm.poster_path}`" alt="poster"></li>
          <li>{{ singleFilm.title }}</li>
          <li>{{ singleFilm.original_title }}</li>
          <li>
            <img class="language"
              v-if="supportedLanguages.includes(singleFilm.original_language)"
              :src="
                require(`../assets/flags/${singleFilm.original_language}.png`)
              "
              alt="language flag"
            />
            <img class="language" v-else :src="require(`../assets/flags/rsw.png`)" alt="rest-of-the-world">
          </li>
          <li>{{ Math.round(singleFilm.vote_average/2) }}</li>
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
    imgBaseUrl: 'https://image.tmdb.org/t/p/',
    };
  },

  props: ["singleFilm"],
};
</script>

<style lang="scss">
 .language {
  width: 4.5rem;
  height: 2.8rem;
}
</style>