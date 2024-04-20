<template>
    <div class="product-card__accordeon flex --direction-column"  :class="{'--isOpen' : isOpen}">
        <div class="product-card__accordeon-head flex --align-center --just-space" @click="toggle">
            <div class="product-card__accordeon-title" v-html="item.title"></div>
            <div class="product-card__accordeon-icon"></div>
        </div>
        <div class="product-card__accordeon-more">
            <p ref="text" v-html="item.text"></p>
        </div>
    </div>
</template>
<script>
    export default {
        data(){
            return {
                isOpen: false
            }
        },
        props:['item'],
        methods: {
            toggle(){
			    this.isOpen = !this.isOpen;
            },
        }
    }
</script>
<style>
    @import '~/components/accordion/__accordion.css';
</style>