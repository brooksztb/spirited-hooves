<script>
export default {
  name: 'App'
};
</script>

<template>
  <v-app>
      <v-content transition="slide-x-transition">
          <router-view></router-view>
      </v-content>
  </v-app>
</template>

<style>
</style>
