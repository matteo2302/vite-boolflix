<script>
import AppMain from './components/AppMain.vue';
import AppHeader from './components/AppHeader.vue';
import { store } from './data/store.js';
import axios from 'axios';

export default {
  data() {
    return {
      query: '',
      language: 'it-IT',
      baseUri: 'https://api.themoviedb.org/3/search',
      apiKey: 'c07677e7edac90efcbbdd18fecf0d93c',
      language: 'language=it-IT'
    }
  },
  components: { AppHeader, AppMain },
  methods: {
    fetchProductions(title) {
      axios.get(`${this.baseUri}/movie?api_key=${this.apiKey}&query=${title}&${this.language}`).then((res) => {
        store.movies = res.data.results;
        console.log('movie', store.movies);
      });

      axios.get(`${this.baseUri}/tv?api_key=${this.apiKey}&query=${title}&${this.language}`).then((res) => {
        store.series = res.data.results;
        console.log('serie', store.series);
      });
    }
  },
}
</script>

<template>
  <header>
    <AppHeader @title-searched="fetchProductions" />
  </header>

  <AppMain />
</template>

<style lang="scss">
@use './assets/scss/style.scss' as *;
</style>