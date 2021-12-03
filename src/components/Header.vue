<template>
  <div class="navigation_bar">
    <div class="title">
      BoolFlix
    </div>
    <div class="search_movies">
      <input type="text" placeholder="Inserisci qui il titolo" v-model="testo" @keyup.enter="$emit('search', testo)">
      <button @click="$emit('search', testo)">Search</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      testo: ""
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.navigation_bar {
  display: flex;
  justify-content: space-around;
  align-items: center;
  width: 100%;
  height: 6vh;
  background-color: rgba(0, 0, 0, 0.336);

  .title {
    color: red;
    font-size: 30px;
    font-family: fantasy;
    border: solid 1px red;
    border-radius: 25px;
    padding: 2px 15px;
  }

  .search_movies {

    input {
      padding: 5px 10px;
      border-radius: 20px;
      color: white;
      background-color: rgba(255, 0, 0, 0);
    }

    button {
      color: white;
      padding: 5px 10px;
      border-radius: 20px;
      background-color: rgba(0, 0, 0, 0);
      cursor: pointer;
    }
  }
}
</style>