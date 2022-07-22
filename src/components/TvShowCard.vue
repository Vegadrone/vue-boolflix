<template>
  <div class="container">
    <div class="row ">
        <div class="col-4">
            <ul>
                 <li>{{singleTvShow.name}} - {{singleTvShow.original_name}} - {{singleTvShow.original_language}} - {{singleTvShow.vote_average}}</li>
            </ul>
        </div>
    </div>
</div>
</template>

<script>
export default {

    props:[
        'singleTvShow'
    ]

}
</script>

<style>

</style>