<template>
  <div class="card-wrapper" :style="{backgroundImage:`url(https://image.tmdb.org/t/p/w342${singleTvShow.poster_path})`}"
  @mouseover="isMouseover = true" @mouseleave="isMouseover = false">
  <h1 class="text-light fw-bold" v-if="singleFilm.poster_path === null">{{singleTvShow.title}}</h1>
    <ul v-show="isMouseover === true">
      <li class="text-light fw-bold">
        Titolo: <span class="fw-normal">{{ singleTvShow.name }}</span>
      </li>
      <li class="text-light fw-bold">
        Titolo Originale:
        <span class="fw-normal">{{ singleTvShow.original_name }}</span>
      </li>
      <li class="text-light fw-bold">Lingua:
        <img
          class="language-icons"
          v-if="supportedLanguages.includes(singleTvShow.original_language)"
          :src="
            require(`../assets/flags/${singleTvShow.original_language}.png`)
          "
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
          v-for="(star, index) in Math.round(singleTvShow.vote_average / 2)"
          :key="index"
        >
        </i>
      </li>
       <li class="text-light fw-bold">Overview: <span class="fw-normal">{{singleTvShow.overview}}</span></li>
    </ul>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      isMouseover:false,
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
.language-icons {
  width: 2.3rem;
  height: 1.5rem;
}
.fa-star {
  color: goldenrod;
}
</style>