<template>
    <footer class="level">
        <div class="level-item" v-for="movie in movies" :key="movie.id">
            <a class="movie-link" tabindex="0">
                <img class="movie-image" :src="movie.thumbnailSrc" />
                <caption class="movie-caption">{{movie.name}}</caption>
            </a>
        </div>
    </footer>
</template>

<script>
import data from '../assets/data.json'

export default {
    data: () => ({
        movies: data,
    }),
}
</script>

<style lang="less" scoped>
@import '../vars';

@link-padding: 3px;

footer {
    height: @footer-height;
    background: #191919;
}

.movie-caption {
    display: none;
}

@media screen and (max-width: 769px) {
    .movie-image {
        display: none;
    }

    .movie-caption {
        display: inherit;
    }
}

.movie-link {
    @overlay-rule: {
        box-shadow: inset 0 0 35px 10px rgba(0, 0, 0, 0.5);
        margin-bottom: 1px;
    }
    ;
    @border-rule: {
        border: 1px solid rgba(72, 181, 255, 0.3);
        border-radius: 3px;
    }
    ;

    .add-overlay(@link-padding, @overlay-rule, @border-rule);
}

.movie-image {
    max-height: @footer-height - 20px;
    width: auto;
}
</style>
