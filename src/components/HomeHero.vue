<script>
let offset = 0;
let call;

export default {
    name: 'HomeHero'
};
</script>

<template>
    <v-container fluid fill-height class="home-hero">
        <v-layout justify-center align-center column pa-5>
            <div class="display-4 font-weight-black white--text text-xs-center">WELCOME TO SPIRITED HOOVES</div>
            <div class="display-4 font-weight-black white--text text-xs-center mb-3">HORSE AND GOAT FARM</div>
            <div class="display-1 font-weight-bold white--text text-xs-center">Come Ride with Us</div>
            <v-btn fab class="mt-5 deep-purple darken-1" v-scroll-to="'#MainInfo'">
                <v-icon large color="white">expand_more</v-icon>
            </v-btn>
        </v-layout>
    </v-container>
</template>

<style scoped>
    .home-hero {
        background: url('../assets/images/backgroundhorses.jpg');
        background-size: cover;
        width: 100%;
        height: 100%;
        max-height: 100vh;
    }
</style>