<script>

import { store } from "../store";

export default {
    data() {
        return {
            store,
            searchText: "",
        }
    },
}
</script>

<template>
    <header class="d-flex align-items-center justify-content-end">
        <nav>
            <input type="search" name="" id="" placeholder="Search" v-model="searchText" @keyup.enter="searchMovies">
            <button type="button" class="ms-2 me-3" @click="searchMovies">Search</button>
        </nav>

        <div v-for="movie in store.movieList" :key="movie.id" :data="movie">
            <p class="text-white">
                {{ movie.title }}
            </p>
        </div>
    </header>
</template>

<style lang="scss" scoped>
header {
    height: 100px;
    background-color: #000;
}
</style>