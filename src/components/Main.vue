<template>
  <div class="movies">
      <Movie v-for="film, i in arrayMovie" 
      :key="i"
      :details="film"/>
  </div>
</template>

<script>
import Movie from '@/components/Movie.vue'

export default {
  name: 'Main',
  components: {
      Movie
  },
  props: {
    arrayMovie: Array
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    .movies {
        display: flex;
        justify-content: flex-start;
        flex-wrap: wrap;
        width: 60%;
        height: 400px;
        background-color: grey;
        margin: 50px auto;
        overflow-y: scroll;
    }
</style>