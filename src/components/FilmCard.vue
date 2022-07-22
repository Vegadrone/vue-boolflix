<template>
  <div class="container">
    <div class="row ">
        <div class="col-4">
            <ul>
                <li>{{singleFilm.title}} - {{singleFilm.original_title}} - {{singleFilm.original_language}} - {{singleFilm.vote_average}}</li>
            </ul>
        </div>
    </div>

  </div>
</template>

<script>
export default {
    props:["singleFilm"]
}
</script>

<style>

</style>