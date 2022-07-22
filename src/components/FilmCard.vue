<template>
  <div class="container">
    <div class="row ">
        <div class="col-4">
            <ul>
                <li>{{singleFilmOrShow.title}} - {{singleFilmOrShow.original_title}} - {{singleFilmOrShow.original_language}} - {{singleFilmOrShow.vote_average}}</li>
            </ul>
        </div>
    </div>

  </div>
</template>

<script>
export default {
    props:["singleFilmOrShow"]
}
</script>

<style>

</style>