<script>

// IMPORT DEL COMPONENTE
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import CardsList from "./components/CardsList.vue";
import Card from "./components/Card.vue";
import axios from "axios"

// DEFINIZIONE DEL COMPONENTE IN PAGINA
export default {

  components: {
    AppHeader, AppMain, CardsList, Card
  },

  methods: {
    getResult() {
      axios.get("https://api.themoviedb.org/3/search/movie?api_key=c62e8b24ab2d74189b7297f58711d77f")
        .then((response) => {
          response.data.response
        })
    }
  }
};
</script>

<template>
  <AppHeader></AppHeader>
  <AppMain></AppMain>
  <CardsList></CardsList>
  <Card></Card>
</template>


<style lang="scss"></style>