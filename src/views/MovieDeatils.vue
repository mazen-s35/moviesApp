<template>
    <div class="movie-details">
        <h2>{{movie.Title}}</h2>
        <p>{{movie.Year}}</p>
        <img :src="movie.Poster" alt="Movie Poster">
        <p>{{movie.Plot}}</p>
    </div>
</template>

<script>
import { ref, onBeforeMount } from 'vue';
import { useRoute } from 'vue-router';
import env from '../env.js';
export default {
    setup() {
        const movie = ref({});
        const route = useRoute();

        onBeforeMount(() => {
        fetch(`http://www.omdbapi.com/?apikey=${env.apikey}&i=${route.params.id}&plot=full`)
        .then(response => response.json())
        .then(data => {
            movie.value = data;
        });
    });

        return {
            movie
        }
    }
}
</script>

<style lang="scss">
    .movie-details {
        padding: 16px;

        h2 {
            color: #fff;
            font: {
                size: 28px;
                weight: 600;
            }
            margin-bottom: 16px;
        }

        img {
            display: block;
            max-width: 200px;
            margin-bottom: 16px;
        }

        p {
            color: #FFF;
            font-size: 18px;
            line-height: 1.4;
        }
    }
</style>