<script>

import { store } from "../data/store";

export default {

    data() {
        return {
            store,
        };
    },

    props: {
        films: Array,
    },
};

</script>

<template>
    <div v-if="films.length">
        <h2>Films</h2>
        <ul v-for="movie in store.movieList" class="mt-4">
            <li>title: {{ movie.title }}</li>
            <li>original_title: {{ movie.original_title }}</li>
            <!-- <li>original_language: {{ movie.original_language }}</li> -->
            <li>
                <img :src="'https://flagsapi.com/BE/flat/64.png'">
            </li>
            <li>vote_average: {{ movie.vote_average }}</li>
        </ul>
    </div>

    <h2>
        Inizia la ricerca
    </h2>
</template>


<style lang="scss" scoped>
ul {
    list-style: none;
}
</style>