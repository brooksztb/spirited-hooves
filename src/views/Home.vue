<script>
  import HomeHero from '@/components/HomeHero';
  import HomeDetails from '@/components/HomeDetails';
  import HomeServices from '@/components/HomeServices';
  import HomeContact from '@/components/HomeContact';

  export default {
      name: 'home',
      components: {
          HomeHero,
          HomeDetails,
          HomeServices,
          HomeContact
      }
  };
</script>

<template>
    <span>
        <home-hero></home-hero>
        <home-details></home-details>
        <home-services></home-services>
        <home-contact></home-contact>
    </span>
</template>
