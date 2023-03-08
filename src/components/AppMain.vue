<script>

import { store } from "../data/store";
import BaseCard from "./BaseCard.vue";

export default {

    data() {
        return {
            store,
        };
    },

    components: {
        BaseCard
    },

    props: {
        films: Array,
    },

};

</script>

<template>
    <div>
        <h2>Films</h2>
        <div class="row row-cols-3">
            <BaseCard v-for="movie in store.movieList" :title="movie.title" :originalTitle="movie.original_title"
                :lang="movie.original_language" :vote="movie.vote_average" />
        </div>
    </div>
</template>


<style lang="scss" scoped>
ul {
    list-style: none;
}
</style>