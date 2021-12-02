<template>
  <div class="movies">
      <Movie v-for="film, i in arrayMovie" 
      :key="i"
      :details="film"/>

      <Serie v-for="serie, i in arraySerie"
      :key="i"
      :details2="serie"/>
  </div>
</template>

<script>
import Movie from '@/components/Movie.vue'
import Serie from '@/components/Serie.vue'
export default {
  name: 'Main',
  components: {
      Movie,
      Serie
  },
  props: {
    arrayMovie: Array,
    arraySerie: Array
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
        height: 600px;
        background-color: grey;
        margin: 50px auto;
        overflow-y: scroll;
    }
</style>