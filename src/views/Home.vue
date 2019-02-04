<script>
  import HomeHero from '@/components/HomeHero';
  import Details from '@/components/Details';
  import Services from '@/components/Services';
  import Contact from '@/components/Contact';

  export default {
      name: 'home',
      components: {
          HomeHero,
          Details,
          Services,
          Contact
      }
  };
</script>

<template>
    <span>
        <home-hero></home-hero>
        <details></details>
        <services></services>
        <contact></contact>
        <v-footer class="pa-3" color="deep-purple darken-1">
            <v-spacer></v-spacer>
            <div class="white--text">&copy; Spirited Hooves {{ new Date().getFullYear() }}</div>
        </v-footer>
    </span>
</template>
