<template>
  <div id="app">
    <PageHeader @searchTitle="search"/>
    <PageMain />
    <CardComponent />
  </div>
</template>

<script>
import axios from 'axios';

import PageHeader from './components/PageHeader.vue';
import PageMain from './components/PageMain.vue';
import CardComponent from './components/CardComponent.vue'


export default {
  name: 'App',
  components: {
    PageHeader,
    PageMain,
    CardComponent
  },
  data: function() {
    return {
      apiUrl: 'https://api.themoviedb.org/3/search/',
      apiKey: '121bc0e4496113720c5608bf27388f16',
      movies: [],
      allResults: [],
      searchStarted: false
    }
  },
  methods: {
    getMovies(apiParams) {
      axios
      .get(this.apiUrl + 'movie', apiParams)
      .then((response) => {

        this.allResults = response.data.results;
        this.searchStarted = true;
      })

    },
    search: function (searchTitle) {

      const paramsObj = {
        params: {
          api_key: this.apikey,
          query: searchTitle,
          language: 'it,IT'
        }
      };

      this.getMovies(paramsObj);
    }
  }
}
</script>

<style lang="scss">
@import './components/style/common.scss';
</style>
