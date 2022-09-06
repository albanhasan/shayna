<template>
    <div class="product-view">
        <HeaderShayna/>
        <!-- Breadcrumb Section Begin -->
        <div class="breacrumb-section">
            <div class="container">
                <div class="row">
                    <div class="col-lg-12">
                        <div class="breadcrumb-text product-more">
                           <router-link to="/"><i class="fa fa-home"></i> Home</router-link>
                            <span>Detail</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>

         <!-- Product Shop Section Begin -->
        <section class="product-shop spad page-details">
            <div class="container">
                <div class="row">
                    <div class="col-lg-12">
                        <div class="row">
                            <div class="col-lg-6">
                                <div class="product-pic-zoom">
                                    <img class="product-big-img" :src="default_image" alt="" />
                                </div>
                                <div class="product-thumbs">
                                    <carousel :items-to-show="3">
                                        <slide v-for="slide in thumbs.length" :key="slide">
                                            <div class="product-item" @click="changeImage(thumbs[slide - 1], $event)">
                                                <div class="pt" :data-imgbigurl="thumbs[slide - 1]">
                                                    <img :src="thumbs[slide - 1]" alt="" />
                                                </div>
                                            </div>
                                        </slide>

                                        <template #addons>
                                            <navigation />
                                        </template>
                                    </carousel>
                                </div>
                            </div>
                            <div class="col-lg-6">
                                <div class="product-details">
                                    <div class="pd-title">
                                        <span>oranges</span>
                                        <h3>Pure Pineapple</h3>
                                    </div>
                                    <div class="pd-desc text-justify">
                                        <p>
                                            Lorem ipsum dolor sit amet consectetur adipisicing elit. Corporis, error officia. Rem aperiam laborum voluptatum vel, pariatur modi hic provident eum iure natus quos non a sequi, id accusantium! Autem.
                                        </p>
                                        <p>
                                            Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quam possimus quisquam animi, commodi, nihil voluptate nostrum neque architecto illo officiis doloremque et corrupti cupiditate voluptatibus error illum. Commodi expedita animi nulla aspernatur.
                                            Id asperiores blanditiis, omnis repudiandae iste inventore cum, quam sint molestiae accusamus voluptates ex tempora illum sit perspiciatis. Nostrum dolor tenetur amet, illo natus magni veniam quia sit nihil dolores.
                                            Commodi ratione distinctio harum voluptatum velit facilis voluptas animi non laudantium, id dolorem atque perferendis enim ducimus? A exercitationem recusandae aliquam quod. Itaque inventore obcaecati, unde quam
                                            impedit praesentium veritatis quis beatae ea atque perferendis voluptates velit architecto?
                                        </p>
                                        <h4>$495.00</h4>
                                    </div>
                                    <div class="quantity">
                                        <router-link to="/shopping-cart"><a href="shopping-cart.html" class="primary-btn pd-cart">Add To Cart</a></router-link>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <RelatedShayna />

        <FooterShayna/>
    </div>
</template>

<script>
import HeaderShayna from '@/components/HeaderShayna.vue';
import FooterShayna from '@/components/FooterShayna.vue';


import 'vue3-carousel/dist/carousel.css';
import { Carousel, Slide, Navigation } from 'vue3-carousel';
import RelatedShayna from '@/components/RelatedShayna.vue';

export default {
    name: "ProductView",
    components: {
    HeaderShayna,
    FooterShayna,
    Carousel,
    Slide,
    Navigation,
    RelatedShayna
},
    data() {
        return {
            default_image : "img/mickey2.jpg",
            thumbs : [
                "img/mickey1.jpg",
                "img/mickey2.jpg",
                "img/mickey3.jpg",
                "img/mickey4.jpg",
            ]
        }
    },
    methods : {
        changeImage(urlImage, event) {
            this.default_image = urlImage;
            var elems = document.querySelectorAll(".product-item");

            //Ini ngga efektif, nnti diganti yaa
            [].forEach.call(elems, function(el) {
                el.childNodes[0].classList.remove("active");
            });

            if(urlImage == this.default_image) {
                event.target.parentElement.classList.add('active');
            }
        }
    }
}
</script>

<style scoped>
    .product-item {
        margin-right: 15px;
    }
</style>