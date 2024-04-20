<template>
    <header class="header grid --temp-col-3 ">
        <div class="header__items-mob header__items --col-1">
            <div v-for="item in items_mob_left" class="header__item">
                <div class="header__item-icon thumb">
                    <NuxtImg :src="item.src"/>
                </div>
            </div>
        </div>
        <div class="header__logo flex --align-center --just-center">
            <div class="header__logo-icon thumb">
                <NuxtPicture src="img/logo.png"/>
            </div>
        </div>
        <div class="header__items flex --just-end --align-center">
            <div v-for="item in items" class="header__item ">
                <div class="header__item-icon thumb">
                    <NuxtImg :src="item.src"/>
                </div>
            </div>
        </div>
        <div class="header__items flex --just-end --align-center header__items-mob">
            <div v-for="item in items_mob_right" class="header__item">
                <div class="header__item-icon thumb">
                    <NuxtImg :src="item.src"/>
                </div>
            </div>
        </div>
    </header>
</template>
<script>
    export default {
        data() {
            return {
                items: [
                    {
                        src:'svg/Search.svg'
                    },
                    {
                        src:'svg/Favorite.svg'
                    },
                    {
                        src:'svg/User.svg'
                    },
                    {
                        src:'svg/Basket.svg'
                    },
                ],
                items_mob_right: [
                    {
                        src:'svg/Basket.svg'
                    },
                ],
                items_mob_left: [
                    {
                        src:'svg/Search.svg'
                    },
                    {
                        src:'svg/User.svg'
                    },
                ],
            }
        },
    }
    
</script>
<style>
        @import '~/components/header/__header.css';
</style>