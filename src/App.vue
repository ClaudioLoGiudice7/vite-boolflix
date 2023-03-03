<script>

// IMPORT DEL COMPONENTE
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import CardsList from "./components/CardsList.vue";
import Card from "./components/Card.vue";

// DEFINIZIONE DEL COMPONENTE IN PAGINA
export default {

  components: {
    AppHeader, AppMain, CardsList, Card
  },

};
</script>

<template>
  <AppHeader></AppHeader>
  <AppMain></AppMain>
  <CardsList></CardsList>
  <Card></Card>
</template>


<style lang="scss"></style>