<script>
  import HomeHero from '@/components/HomeHero';
  import About from '@/components/About';
  import Services from '@/components/Services';
  import Contact from '@/components/Contact';

  export default {
      name: 'home',
      components: {
          HomeHero,
          About,
          Services,
          Contact
      }
  };
</script>

<template>
    <span>
        <home-hero></home-hero>
        <about></about>
        <services></services>
        <contact></contact>
        <v-footer class="pa-3" color="deep-purple darken-1">
            <v-spacer></v-spacer>
            <div class="white--text">&copy; Spirited Hooves {{ new Date().getFullYear() }}</div>
        </v-footer>
    </span>
</template>
