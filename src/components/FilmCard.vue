<template>
  <div
    class="card-wrapper"
    :style="{
      backgroundImage: `url(https://image.tmdb.org/t/p/w342${singleFilm.poster_path})`,
    }"
    @mouseover="isMouseover = true"
    @mouseleave="isMouseover = false"
  >
    <h1 class="text-light fw-bold" v-if="singleFilm.poster_path === null">
      {{ singleFilm.title }}
    </h1>
    <ul v-show="isMouseover === true">
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
      <li class="text-light fw-bold">
        Overview: <span class="fw-normal">{{ singleFilm.overview }}</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      isMouseover: false,
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
  width: 2.3rem;
  height: 1.5rem;
}

.fa-star {
  color: goldenrod;
}

.card-wrapper {
  background-repeat: no-repeat;
  background-size: cover;
  height: 40rem;
  position: relative;
  border: 2px solid red;
  cursor: pointer;

  ul {
    font-size: 1.12rem;
    padding: 1.5rem;
    position: absolute;
    top: 0;
    left: 0;
    background-color: #030303;
    height: 100%;
    width: 100%;
    overflow-y: auto;
  }
}
</style>