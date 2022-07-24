<template>
  <div class="card-wrapper" :style="{backgroundImage:`url(https://image.tmdb.org/t/p/w342${singleFilm.poster_path})`}">
    <ul>
      <li class="text-light fw-bold">
        Titolo: <span class="fw-normal">{{ singleFilm.title }}</span>
      </li>
      <li class="text-light fw-bold">
        Titolo originale:
        <span class="fw-normal">{{ singleFilm.original_title }}</span>
      </li>
      <li class="text-light fw-bold">
        Lingua:
        <img
          class="language-icons"
          v-if="supportedLanguages.includes(singleFilm.original_language)"
          :src="require(`../assets/flags/${singleFilm.original_language}.png`)"
          alt="language flag"
        />
        <img
          class="language-icons"
          v-else
          :src="require(`../assets/flags/rsw.png`)"
          alt="rest-of-the-world"
        />
      </li>
      <li class="text-light fw-bold">
        Voto:
        <i
          class="fa-solid fa-star"
          v-for="(star, index) in Math.round(singleFilm.vote_average / 2)"
          :key="index"
        ></i>
      </li>
      <li class="text-light fw-bold">Overview <span class="fw-normal">{{singleFilm.overview}}</span></li>
    </ul>
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

  props: ["singleFilm"],
};
</script>

<style lang="scss">

.language-icons {
  width: 4.5rem;
  height: 2.8rem;
}

.fa-star {
  color: goldenrod;
}

.card-wrapper{
  background-repeat: no-repeat;
  background-size: cover;
  height: 40rem;
}

</style>