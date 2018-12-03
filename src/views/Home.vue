<script>
  import HomeHero from '@/components/HomeHero';
  import HomeDetails from '@/components/HomeDetails';
  import HomeServices from '@/components/HomeServices';

  export default {
      name: 'home',
      components: {
          HomeHero,
          HomeDetails,
          HomeServices
      }
  };
</script>

<template>
    <span>
        <home-hero></home-hero>
        <home-details></home-details>
        <home-services></home-services>
    </span>
</template>
