<script>
export default {
    name: 'HomeHero'
};
</script>

<template>
    <v-container fluid fill-height class="home-hero" id="MainInfo" style="max-height: 100vh;">
        <v-layout justify-center align-center column pa-5>
            <div class="home-hero-header display-4 font-weight-black white--text text-xs-center">WELCOME TO SPIRITED HOOVES</div>
            <div class="home-hero-header display-4 font-weight-black white--text text-xs-center mb-3">HORSE AND GOAT FARM, LLC</div>
            <div class="home-hero-subheader display-1 font-weight-bold white--text text-xs-center">Come Ride with Us</div>
            <v-btn fab class="mt-5 deep-purple darken-1" v-scroll-to="'#AboutUs'">
                <v-icon large color="white">expand_more</v-icon>
            </v-btn>
        </v-layout>
    </v-container>
</template>

<style scoped>
    .home-hero {
        background: linear-gradient(to top, rgba(0, 0, 0, 0.32), rgba(0, 0, 0, 0.32)), url('../assets/images/backgroundhorses.jpg');
        background-size: cover;
        width: 100%;
        height: 100%;
    }

    @media (max-width: 600px) {
        .home-hero-header {
            font-size: 45px !important;
        }

        .home-hero-subheader {
            font-size: 24px !important;
        }   
    }
    
</style>