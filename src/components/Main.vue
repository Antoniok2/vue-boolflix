<template>
  <div class="movies">
    <Movie v-for="film, i in arrayMovie" 
    :key="'film' + i"
    :details="film"/>

    <Serie v-for="serie, i in arraySerie"
    :key="'serie' + i"
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
  width: 100%;
  height: 80vh;
  background-color: rgba(0, 0, 0, 0.616);
  margin: 50px auto;
  overflow-y: scroll;
}

::-webkit-scrollbar {
  width: 2px;
}

::-webkit-scrollbar-thumb {
  background: red;
  border-radius: 10px;
}
</style>