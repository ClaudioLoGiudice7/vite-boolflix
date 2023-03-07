<script>

// IMPORT DEL COMPONENTE
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import { store } from "./data/store"

import axios from "axios"

// DEFINIZIONE DEL COMPONENTE IN PAGINA
export default {

  data() {
    return {
      store
    };
  },

  components: {
    AppHeader, AppMain
  },

  methods: {
    searchMovies(performSearch) {
      axios
        .get(
          `${store.BaseURI}/search/movie?&api_key=${store.apiKey}&query=${performSearch}`
        )
        .then((response) => {
          store.movieList = response.data.results;
          console.log(store.movieList);
        })
    }
  }
};

</script>

<template>
  <AppHeader @performSearch="searchMovies" />
  <AppMain :films="store.movieList" />
</template>


<style lang="scss"></style>