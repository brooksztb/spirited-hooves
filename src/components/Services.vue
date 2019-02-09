<script>
    export default {
        name: 'Services',
        data() {
            return {
                hayChixImgs: [
                    {src: require('@/assets/images/haychix/HayChixNet-Overcast.png')},
                    {src: require('@/assets/images/haychix/HayChixNet-Winter.jpg')},
                    {src: require('@/assets/images/haychix/HayChixNet-BarnStall.png')},
                    {src: require('@/assets/images/haychix/HayChixNet-Winter2.jpg')}
                ],
                boardingImgs: [
                    {src: require('@/assets/images/arena/Arena1.jpg')},
                    {src: require('@/assets/images/barn/OutsideStall.jpg')},
                    {src: require('@/assets/images/barn/Stall-Outdoor-Empty.png')},
                    {src: require('@/assets/images/barn/Barn.jpg')},
                    {src: require('@/assets/images/barn/OutsideBarn.jpg')}
                ]
            }
        }
    };
    //TODO: Create Reuseable Component to Pull images and associated text with the available services
</script>

<template>
    <v-container grid-list-lg id="Services">
        <v-layout row>
            <v-flex xs12 class="text-xs-center display-1 font-weight-bold grey--text text--darken-3 my-5">Available Services</v-flex>
        </v-layout>
        <v-layout row wrap align-center justify-center>
            <v-flex xs12 sm12 md12>
                <v-card>
                    <v-carousel :hide-controls="true" :cycle="false" class="services-carousel" :height="600"> 
                        <v-carousel-item
                        v-for="(boardingImg,i) in boardingImgs"
                        :key="i"
                        :src="boardingImg.src"
                        ></v-carousel-item>
                    </v-carousel>

                    <v-card-title primary-title>
                        <div>
                            <h3 class="grey--text text--darken-3 headline mb-0">Boarding Options Available & Costs</h3>
                            <p class="grey--text text--darken-3">
                                Pasture boarding with sheds, Box stalls with daily turn out, 150’ x 200’ outdoor arena, a 50’ round pen, 
                                and trail riding around the property.
                                Monthly board includes good quality grass hay and blanketing as needed. Grain and supplements
                                are supplied by the animal’s owner and will be fed as instructed. Owner lives on property and 
                                free trailer parking is available. <b>*Rates are subject to change</b>.
                            </p>
                        </div>
                    </v-card-title>
                </v-card>
            </v-flex>

            <!--Haychix Nets Section-->
            <v-flex xs12 sm12 md12>
                <v-card>
                    <v-carousel :hide-controls="true" :cycle="false" class="services-carousel" :height="600"> 
                        <v-carousel-item
                        v-for="(hayChixImg,i) in hayChixImgs"
                        :key="i"
                        :src="hayChixImg.src"
                        ></v-carousel-item>
                    </v-carousel>
                    <v-card-title primary-title>
                        <div>
                            <h3 class="grey--text text--darken-3 headline mb-0">Hay Chix Nets</h3>
                            <p class="grey--text text--darken-3">
                                Spirited Hooves is also an authorized Hay Chix dealer. Providing Hay Nets feeders for your horses. 
                                Options include Hay Nets by Flake, Square Bale, or Round Bale. <b>*Inquire for Prices.</b>
                            </p>
                        </div>
                    </v-card-title>
                </v-card>
            </v-flex>

            <!--Special Needs Horses Section-->
            <v-flex xs12 sm12 md12>
                <v-card>
                    <v-img class="services-self-care-img" :src="require('@/assets/images/horses/TrainerWithHorse.jpg')" position="center top">
                    </v-img>
                    <v-card-title primary-title>
                        <div>
                            <h3 class="grey--text text--darken-3 headline mb-0">Self Care</h3>
                            <p class="grey--text text--darken-3">
                                Are you interested in self-care for your animal? We have 5 acres available with lots of shelter for self-care. Water and electricity
                                are available in these spaces. Horse owner would be in charge of providing all hay and grain, feeding and all care of their
                                own animals, including all mucking. This would be for 2 or more horses.
                            </p>
                        </div>
                    </v-card-title>
                </v-card>
            </v-flex>

            
        </v-layout>
    </v-container>
</template>

<style scoped>
    .services-self-care-img {
        height: 600px !important;
    }

    @media (max-width: 600px) {
        .services-self-care-img,
        .services-carousel {
            height: 450px !important;
        }

        .services-carousel /deep/ .v-responsive.v-image.v-carousel__item {
            height: 450px !important;
        }
    }
</style>