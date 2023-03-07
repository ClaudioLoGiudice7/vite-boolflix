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

    methods: {
        getFlag(country) {
            country = country.toUpperCase();

            if (country == "EN") return "https://flagsapi.com/GB/flat/64.png"
            return "https://flagsapi.com/" + country + "/flat/64.png";
        }
    }
};

</script>

<template>
    <div>
        <h2>Films</h2>
        <ul v-for="movie in store.movieList" class="mt-4">
            <li>title: {{ movie.title }}</li>
            <li>original_title: {{ movie.original_title }}</li>
            <!-- <li>original_language: {{ movie.original_language }}</li> -->
            <li>
                <img :src="getFlag(movie.original_language)">
            </li>
            <li>vote_average: {{ movie.vote_average }}</li>
        </ul>
    </div>
</template>


<style lang="scss" scoped>
ul {
    list-style: none;
}
</style>