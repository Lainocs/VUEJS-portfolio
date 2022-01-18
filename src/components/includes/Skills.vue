<template>
    <div class="content">
        <h2>Skills</h2>
        <div class="card p-3">

            <Splide :options="{ rewind: true, autoplay: true, width: '70vw' }">
                <SplideSlide class="tab">
                    <img :src="require('@/assets/images/skills/javascript.png')" alt="javascript">
                    <Javascript />
                </SplideSlide>
                <SplideSlide class="tab">
                    <img :src="require('@/assets/images/skills/php.png')" alt="php">
                    <Php />
                </SplideSlide>
                <SplideSlide class="tab">
                    <img :src="require('@/assets/images/skills/laravel.png')" alt="laravel">
                    <Laravel />
                </SplideSlide>
                <SplideSlide class="tab">
                    <img :src="require('@/assets/images/skills/symfony.png')" alt="symfony">
                    <Symfony />
                </SplideSlide>
                <SplideSlide class="tab">
                    <img :src="require('@/assets/images/skills/vue-js.png')" alt="vue-js">
                    <Vue />
                </SplideSlide>
                <SplideSlide class="tab">
                    <img :src="require('@/assets/images/skills/wordpress.png')" alt="wordpress">
                    <Wordpress />
                </SplideSlide>
            </Splide>
        </div>
    </div>
</template>

<script>
import '@splidejs/splide/dist/css/splide.min.css';
import { Splide, SplideSlide } from '@splidejs/vue-splide';
import Php from "./skills/php.vue"
import Javascript from "./skills/javascript.vue";
import Laravel from "./skills/laravel.vue";
import Symfony from "./skills/symfony.vue";
import Vue from "./skills/vuejs.vue";
import Wordpress from "./skills/wordpress.vue";
    export default {
    name: "Skills",
    components: { Php, Javascript, Laravel, Symfony, Vue, Wordpress, Splide, SplideSlide },
    data() {
        return {
            activePage: "javascript",
        };
    },
}
</script>

<style lang="scss">
    h2 {
        text-decoration: underline;
        text-underline-offset: 20px;
    }
    .tab {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        margin: 50px auto;
        img {
            height: 150px;
        }
    }
    .card {
        min-height: 50vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        border-radius: 20px;
        padding: 20px;
        .nav-tabs {
            list-style: none;
            display: flex;
            
            
        }
    }
</style>