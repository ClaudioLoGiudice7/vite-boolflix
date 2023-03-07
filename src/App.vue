<script>

// IMPORT DEL COMPONENTE
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import { store } from "./store"

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
    searchMovies() {
      axios
        .get(
          `${store.BaseURI}/search/movie?&api_key=${store.apiKey}&query=${this.searchText}`
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
  <AppHeader @performSearch="" />
  <AppMain :films="store.movieList"></AppMain>
</template>


<style lang="scss"></style>