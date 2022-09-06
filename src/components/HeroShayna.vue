<template>
    <div>
        <carousel>
            <slide v-for="slide in 10" :key="slide">
                <div class="hero-items">
                    <div class="single-hero-items set-bg" style="background-image:url('img/hero-1.jpg')">
                        <div class="container">
                            <div class="row">
                                <div class="hero-text col-lg-5">
                                    <span>Bag,kids</span>
                                    <h1> {{ slide }}</h1>
                                    <p>
                                        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore
                                    </p>
                                    <a href="#" class="primary-btn">Shop Now</a>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            
            </slide>

            <template #addons>
                <navigation />
                <pagination />
            </template>
        </carousel>
    </div>    
</template>

<script>

import 'vue3-carousel/dist/carousel.css';
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel';

export default {
    name: 'HeroShayna',
    components: {
        Carousel,
        Slide,
        Pagination,
        Navigation
    }
}
</script>


<style scoped>
    .hero-items {
      width: 100%;
    }
    
    .hero-items .hero-text > * {
      opacity: 1;
      text-align: left;
    }
    .carousel {
      text-align: initial;
    }
</style>
    