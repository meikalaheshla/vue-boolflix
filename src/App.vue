<template>
  <div id="app">
    <input type="text" @keyup.enter="getFilmsList" v-model="searchTxt"><button @click="getFilmsList">cerca</button>
    <div>
      <h2>FILM</h2>
      <ul>
        <li v-for="film in films" :key="film.id">
          <span>Titolo:{{ film.title }}</span><br>
          <span>Titolo originale:{{ film.original_title }}</span><br>
          <span>Lingua:{{ film.language }}</span><br>
          <span>Voto:{{ film.vote_average }}</span><br>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import axios from 'axios';


export default {
  name: 'App',
  components: {

  }, data() {
    return {
      films: [],
      searchTxt: '',
    }
  }, methods: {
    fetchFilms() {

    },
    getFilmsList() {
      const config = {
        params: {
          api_key: '7bcf8d53204c83d72c3d8fe0f87098a1',
          query: this.searchTxt,
          language: 'it-IT'

        }
      }
      axios
        .get('https://api.themoviedb.org/3/search/movie', config)
        .then((res) => {
          this.films = res.data.results
        })




    }

  }

}
</script>

<style lang="scss">
</style>
