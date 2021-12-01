<template>
  <div class="movies">
      <Movie/>
  </div>
</template>

<script>
import Movie from '@/components/Movie.vue'

export default {
  name: 'Main',
  components: {
      Movie
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    .movies {
        display: flex;
        justify-content: flex-start;
        width: 60%;
        height: 400px;
        background-color: grey;
        margin: 50px auto;
    }
</style>