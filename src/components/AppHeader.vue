<script>
export default {
    data() {
        return {

        }
    },

    methods: {
        getResult() {
            axios.get("https://api.themoviedb.org/3/search/movie?api_key=c62e8b24ab2d74189b7297f58711d77f")
                .then((response) => {
                    response.data.response
                })
        }
    }
}
</script>

<template>
    <header class="d-flex align-items-center justify-content-end">
        <nav>
            <input type="search" name="" id="">
            <button type="button" class="ms-2 me-3" @click="getResult()">Search</button>
        </nav>
    </header>
</template>

<style lang="scss" scoped>
header {
    height: 100px;
    background-color: #000;
}
</style>
