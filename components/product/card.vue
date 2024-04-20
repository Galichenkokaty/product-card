<template>
    <div class="product-card center-wrap col --12 flex --direction-column">
        <div class="product-card__content flex">
            <div class="swiper product-card__gallery flex swiper-container">
                <div class="swiper-wrapper">
                    <div v-for="src in carusel_img" class="swiper-slide product-card__gallery-full thumb">
                        <NuxtPicture :src="src.src"/>
                    </div>
                </div>
                <div class="swiper-pagination-img">
                    <div class="swiper-wrapper">
                        <div  v-for="src in carusel_img" class="product-card__gallery-mini-img thumb swiper-slide">
                            <span class="product-card__gallery-mini-mask"></span>
                            <NuxtPicture :src="src.src"/>
                        </div>
                    </div>
                </div>
            </div>
            <div class="product-card__info flex --direction-column">
                <div class="product-card__head flex --direction-column">
                    <h1 class="product-card__title">ЖАКЕТ УДЛИНЁННЫЙ, БЕЛЫЙ</h1>
                    <p class="product__card__price">8900 RUB</p>
                </div>
                <div class="product-card__size flex --direction-column">
                    <p class="product-card-size-title">Размеры</p>
                    <div class="product-card__size-cards flex">
                        <div class="product-card__size-card ">XS</div>
                        <div class="product-card__size-card">S</div>
                        <div class="product-card__size-card">M</div>
                    </div>
                </div>
                <div class="product-card__color flex --direction-column">
                    <p class="product-card__color-title">Цвет: </p>
                    <div class="product-card__color-cards flex">
                        <div class="product-card__color-card --white" style="background-color: #FFFFFF;"></div>
                        <div class="product-card__color-card --is-active" style="background-color: #000000;"></div>
                        <div class="product-card__color-card " style="background-color: #F9F1DC;"></div>
                    </div>
                </div>
                <div class="product-card__events flex">
                    <button class="product-card__basket flex --align-center --just-center">Добавить в корзину</button>
                    <button class="product-card__favorite flex --align-center --just-center">
                        <NuxtImg class="product-card__favorite-icon thumb" src="svg/Favorite.svg"/>
                    </button>
                </div>
                <div class="product-card__accordions flex --direction-column">
                    <Accordion v-for="item in accordions" :item="item" :key="item.id" />
                </div>
            </div>
        </div>
        <div class="product-card__similar flex --direction-column">
            <h3 class="product-card__similar-title">Похожие товары</h3>
            <ProductCarusel/>
        </div>
    </div>
</template>
<script>
    import Swiper from 'swiper'
    import { Navigation, Pagination, Thumbs  } from 'swiper';
    import 'swiper/swiper-bundle.css'
    Swiper.use([Navigation, Pagination, Thumbs ]);

    export default {
        data() {
            return {
                accordions: [
                    {
                        "title": "Описание",
                        "text": "Сайт рыбатекст поможет дизайнеру, верстальщику, вебмастеру сгенерировать несколько абзацев более менее осмысленного текста рыбы на русском языке, а начинающему оратору отточить навык публичных выступлений в домашних условиях. При создании генератора мы использовали небезизвестный универсальный код речей. Текст генерируется абзацами случайным образом от двух до десяти предложений в абзаце, что позволяет сделать текст более привлекательным и живым для визуально-слухового восприятия.",
                    },
                    {
                        "title": "Состав и уход",
                        "text": "Сайт рыбатекст поможет дизайнеру, верстальщику, вебмастеру сгенерировать несколько абзацев более менее осмысленного текста рыбы на русском языке, а начинающему оратору отточить навык публичных выступлений в домашних условиях. При создании генератора мы использовали небезизвестный универсальный код речей. Текст генерируется абзацами случайным образом от двух до десяти предложений в абзаце, что позволяет сделать текст более привлекательным и живым для визуально-слухового восприятия.",
                    },
                ],
                carusel_img:[
                    {
                        src: 'img/product/product-1-img-1.jpg'
                    },
                    {
                        src: 'img/product/product-1-img-2.jpg'
                    },
                    {
                        src: 'img/product/product-1-img-3.jpg'
                    },
                ]
            }
        },
        mounted(){
            const swiper2 = new Swiper('.swiper-pagination-img', {
                slidesPerView: "auto",
                spaceBetween: 10,
                direction: "vertical", 
            });
            const swiper = new Swiper('.product-card__gallery', {
                slidesPerView: 1,
                spaceBetween: 10,
                thumbs: {
                    swiper: swiper2,
                    slideThumbActiveClass: 'swiper-slide-thumb-active',
                },
                breakpoints:{
                    640:{
                        direction: "vertical",
                    }
                }
            });
        }
    }
    
</script>
<style>
    @import '~/components/product/__product.css';
</style>