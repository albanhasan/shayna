<template>
    <div>
        <Carousel :items-to-show="3" :wrap-around="true">
            <slide v-for="slide in 10" :key="slide">
                <div class="hero-items">
                    <div class="product-item">
                        <div class="pi-pic">
                            <img src="img/mickey1.jpg" alt="" />
                            <ul>
                                <li class="w-icon active">
                                    <a href="#"><i class="icon_bag_alt"></i></a>
                                </li>
                                <li class="quick-view"><router-link to="/product">+ Quick View</router-link></li>
                            </ul>
                        </div>
                        <div class="pi-text">
                            <div class="catagory-name">Coat</div>
                            <router-link to="/product">
                                <h5>Mickey Baggy</h5>
                            </router-link>
                            <div class="product-price">
                                $14.00
                                <span>$35.00</span>
                            </div>
                        </div>
                    </div>
                </div>
            
            </slide>

            <template #addons>
                <navigation/>
                <pagination />
            </template>
        </carousel>
    </div>
</template>

<script>
import 'vue3-carousel/dist/carousel.css';
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel';

export default {
    name: 'WomanShayna',
    components: {
        Carousel,
        Slide,
        Pagination,
        Navigation
    }
}
</script>

<style scoped>
.product-item {
    width: 570px;
}
</style>