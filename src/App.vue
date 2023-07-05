<script>
import AppSearch from './AppSearch.vue';
import AppMain from './AppMain.vue';
import { store } from './data/store.js';
import axios from 'axios';

export default {
  data() {
    return {
      query: '',
      language: 'it-IT',
      movie: 'movie',
      series: 'tv'
    }
  },
  components: { AppSearch, AppMain },
  // methods() {
  //   // monto l'endpoint con il parametro dinamico
  //   const filteredUriFilms = `${this.baseUri}/search/movie?api_key=${this.api_key}&query=${string}&language=it-IT`
  //   const filteredUriSeries = `${this.baseUri}/search/tv?api_key=${this.api_key}&query=${string}&language=it-IT`

  //   console.log(filteredUriFilms)
  //   console.log(filteredUriSeries)
  //   // richiamo la funzione che ha la call usando l'endpoint nuovo
  //   this.fetchFilms(filteredUriFilms)
  //   this.fetchSeries(filteredUriSeries)
  // },
  created() {
    let searchType = this.movie;
    let endpoint = `https://api.themoviedb.org/3/search/${searchType}?api_key=c07677e7edac90efcbbdd18fecf0d93c&query=anelli&language=it-IT`;
    axios.get(endpoint).then((res) => {
      store.movies = res.data.results;

      console.log('movie', store.movies);
    });
    searchType = this.series;
    endpoint = `https://api.themoviedb.org/3/search/${searchType}?api_key=c07677e7edac90efcbbdd18fecf0d93c&query=anelli&language=it-IT`;
    axios.get(endpoint).then((res) => {
      store.series = res.data.results;

      console.log('serie', store.series);
    });
  }
}
</script>

<template>
  <div class="container">
    <AppSearch />
    <AppMain />
  </div>
</template>

<style></style>