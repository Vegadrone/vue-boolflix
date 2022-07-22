<template>
  <div class="container">
    <div class="row">
      <div class="col-4">
        <ul>
          <li>{{ singleTvShow.name }}</li>
          <li>{{ singleTvShow.original_name }}</li>
          <li>
            <img
              v-if="languages.includes(singleTvShow.original_language)"
              :src="
                require(`../assets/flags/${singleTvShow.original_language}.png`)
              "
              alt="language flag"
            />
            <img
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

    data:function(){
        return{
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
        }
    },

  props: ["singleTvShow"],

  methods: {},
};
</script>

<style lang="scss">
</style>