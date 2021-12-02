<template>
  <div id="app">

    <header>
      <Header @search="movie"/>
    </header>

    <main>
      <Main :arrayMovie="movies" :arraySerie="series"/>
    </main>

  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import axios from "axios"
export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data() {
    return {
      apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=ae7524e40cf6c1c524835fa04e42516e",
      apiUrlSeries: "https://api.themoviedb.org/3/search/tv?api_key=ae7524e40cf6c1c524835fa04e42516e",
      query: "&query=",
      language: "&language=it-IT",
      page: "&page=1",
      movies: [],
      series: [],
      inputUtente: ""
    }
  },
  methods: {
    // IN QUESTO MODO ATTRAVERSO L'INPUT DELL'UTENTE VADO A FARE UNA CHIAMATA API PER RICAVARMI I Dati DEL TITOLO CERCATO e salvo dutto dentro l'array precedentemente creata
    movie(testo) {
      this.inputUtente = testo;
      console.log(this.inputUtente);
      axios
      .get(this.apiUrl + this.language + this.page + this.query + this.inputUtente)
      .then((result) => {
        // console.log(result.data.results);
        this.movies = result.data.results;
        console.log(this.movies)
      }
      ),
      this.inputUtente = testo;
      axios
      .get(this.apiUrlSeries + this.language + this.page + this.query + this.inputUtente)
      .then((result) => {
        this.series = result.data.results;
        console.log(this.series);
      })
    },
  }
}
</script>

<style lang="scss">

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: black;
  height: 100vh;
}
</style>