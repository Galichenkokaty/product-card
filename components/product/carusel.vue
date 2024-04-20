<template>
    <div class="swiper product-card__carusel swiper-container">
        <div class="swiper-pagination"></div>
        <div class="swiper-wrapper">
            <div v-for="card in cards" class="swiper-slide product-card__carusel-slide flex --direction-column">
                <div class="product-card__carusel-slide-img thumb">
                    <NuxtPicture :src="card.src"/>
                </div>
                <div class="product-card__carusel-slide-head flex --direction-column">
                    <h2 class="product-card__carusel-slide-title" v-html="card.title"></h2>
                    <p class="product-card__carusel-slide-price">
                        {{ card.price }} RUB
                        <del v-if="card.old_price" class="product-card__carusel-slide-old-price">{{ card.old_price }} RUB</del>
                    </p>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    import Swiper from 'swiper'
    import { Navigation, Pagination } from 'swiper';
    import 'swiper/swiper-bundle.css'
    Swiper.use([Navigation, Pagination]);
    
    export default{
        data(){
            return {
                cards:[
                    {
                        src:'img/product/product-2-img-1.jpg',
                        title:'платье в v-образным вырезом, белый',
                        price:'14 900',
                        old_price:'8 000'
                    },
                    {
                        src:'img/product/product-3-img-1.jpg',
                        title:'жакет двубортный, серо-голубой',
                        price:'8 900'
                    },
                    {
                        src:'img/product/product-4-img-1.jpg',
                        title:'платье макси с ярусами, белый',
                        price:'10 500',
                    },
                    {
                        src:'img/product/product-5-img-1.jpg',
                        title:'комбинезон со стойкой, черный',
                        price:'9 500',
                    },
                ]
            }
        },
        mounted(){
            const swiper = new Swiper('.product-card__carusel', {
                slidesPerView: 2,
                spaceBetween: 10,

                // If we need pagination
                pagination: {
                    el: '.swiper-pagination',
                    type: 'bullets',
                    clickable: true
                },
                breakpoints:{
                    990:{
                        slidesPerView: 4,
                    },
                    640:{
                        slidesPerView: 3,
                    },

                }
            });
        }
    }
</script>