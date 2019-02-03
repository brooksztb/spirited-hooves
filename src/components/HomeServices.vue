<script>
    export default {
        name: 'HomeServices',
        data() {
            return {
                hayChixImgs: [
                    {src: require('@/assets/images/haychix/HayChixNet-Overcast.png')},
                    {src: require('@/assets/images/haychix/HayChixNet-Winter.jpg')},
                    {src: require('@/assets/images/haychix/HayChixNet-BarnStall.png')},
                    {src: require('@/assets/images/haychix/HayChixNet-Winter2.jpg')}
                ],
                boardingImgs: [
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
            <v-flex xs12 class="text-xs-center display-1 font-weight-black my-5">Available Services</v-flex>
        </v-layout>
        <v-layout row wrap>
            <v-flex xs12 sm12 md12>
                <v-card>
                    <v-carousel :hide-controls="true" :cycle="false"> 
                        <v-carousel-item
                        v-for="(boardingImg,i) in boardingImgs"
                        :key="i"
                        :src="boardingImg.src"
                        ></v-carousel-item>
                    </v-carousel>

                    <v-card-title primary-title>
                        <div>
                            <h3 class="headline mb-0">Boarding Options Available</h3>
                            <div>
                                Pasture boarding with sheds, Box stalls with daily turn out, 150’ x 200’ outdoor arena, and a 50’ round pen.
                                Monthly board includes good quality grass hay and blanketing as needed. Grain and supplements are supplied by the animal’s owner and will be fed as instructed. Owner lives on property. Free Trailer Parking. *Rates are subject to change.
                            </div>
                        </div>
                    </v-card-title>
                </v-card>
            </v-flex>

            <!--Haychix Nets Section-->
            <v-flex xs12 sm12 md12>
                <v-card>
                    <v-carousel :hide-controls="true" :cycle="false"> 
                        <v-carousel-item
                        v-for="(hayChixImg,i) in hayChixImgs"
                        :key="i"
                        :src="hayChixImg.src"
                        ></v-carousel-item>
                    </v-carousel>
                    <v-card-title primary-title>
                        <div>
                            <h3 class="headline mb-0">Hay Chix Nets</h3>
                            <div>
                                Spirited Hooves is also an authorized Hay Chix dealer. Providing Hay Net feeders for your horses. Options include Hay Nets by Flake, Square Bale, or Round Bale. *Inquire for Prices.
                            </div>
                        </div>
                    </v-card-title>
                </v-card>
            </v-flex>

            <!--Special Needs Horses Section-->
            <v-flex xs12 sm12 md12>
                <v-card>
                    <v-img :src="require('@/assets/images/horses/TrainerWithHorse.jpg')" height="500px">
                    </v-img>
                    <v-card-title primary-title>
                        <div>
                            <h3 class="headline mb-0">Self Care</h3>
                            <div>
                                Info About this needed
                            </div>
                        </div>
                    </v-card-title>
                </v-card>
            </v-flex>

            
        </v-layout>
    </v-container>
</template>

<style scoped>
</style>