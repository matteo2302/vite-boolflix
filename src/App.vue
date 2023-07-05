<script >
let endpoint = 'https://api.themoviedb.org/3/search//api-key=c07677e7edac90efcbbdd18fecf0d93c';

import { store } from './data/store.js'
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
  created() {
    let searchType = this.movie;
    endpoint = `https://api.themoviedb.org/3/search/${searchType}?api_key=c07677e7edac90efcbbdd18fecf0d93c`;

    axios.get(endpoint, {
      params: {
        query: this.query,
        language: this.language
      }
    }).then((res) => {
      store.movies = res.data.results
      console.log(res.data);
      console.log(store.movies);
    })
  }
}
</script>

<template></template>

<style></style>
