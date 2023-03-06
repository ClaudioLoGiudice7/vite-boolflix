<script>

// IMPORT DEL COMPONENTE
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import AppCard from "./components/AppCard.vue";
import { store } from "./store";

// DEFINIZIONE DEL COMPONENTE IN PAGINA
export default {
  data() {
    return {
      store
    }
  },

  components: {
    AppHeader, AppMain, AppCard
  },

};
</script>

<template>
  <AppHeader></AppHeader>
  <AppMain></AppMain>
  <AppCard></AppCard>
</template>


<style lang="scss"></style>