<template>
  <div class="container">
    <div class="row ">
        <div class="col-4">
            <ul>
                <li>{{singleFilmFromApi.title}}</li>
                <li>{{singleFilmFromApi.original_title}}</li>
                <li>{{singleFilmFromApi.original_language}}</li>
                <li>{{singleFilmFromApi.vote_average}}</li>
            </ul>
        </div>
    </div>

  </div>
</template>

<script>
export default {
    props:["singleFilmFromApi"]
}
</script>

<style>

</style>