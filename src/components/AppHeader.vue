<script>

import { store } from "../store";

export default {
    data() {
        return {
            store,
            searchText: "",
        }
    },

    emits: ["performSearch"],
}
</script>

<template>
    <header class="d-flex align-items-center justify-content-end">

        <nav class="navbar">
            <div class="container-fluid">
                <form class="d-flex" role="search" @submit.prevent="$emit('performSearch', searchText)">
                    <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search"
                        v-model="searchText" @keyup.enter="searchMovies">
                    <button class="btn btn-outline-success" type="submit" @click="searchMovies">Search</button>
                </form>
            </div>
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