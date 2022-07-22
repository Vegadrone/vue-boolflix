<template>
  <div class="container">
    <div class="row ">
        <div class="col-4">
            <ul>
                <li>{{singleFilmFromApi.title}} - {{singleFilmFromApi.original_title}} - {{singleFilmFromApi.original_language}} - {{singleFilmFromApi.vote_average}}</li>
                 <li>{{singleFilmFromApi.name}} - {{singleFilmFromApi.original_name}} - {{singleFilmFromApi.original_language}} - {{singleFilmFromApi.vote_average}}</li>
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