<script>
import Navigation from '@/components/Navigation';

export default {
    name: 'App',
    components: {
        Navigation
    }
};
</script>

<template>
  <v-app id="app">
    <navigation></navigation>

    <v-content transition="slide-x-transition">
        <router-view></router-view>
    </v-content>
  </v-app>
</template>

<style>
</style>
