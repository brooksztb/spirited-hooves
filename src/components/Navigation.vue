<script>
export default {
  name: 'Navigation',
  data() {
    return {
      appTitle: 'Spirited Hooves',
      drawer: false,
      items: [
          { title: 'Menu' }, 
          { title: 'Services' }, 
          { title: 'Contact' }
        ]
    };
  }
};
</script>

<template>
    <div>   
        <v-navigation-drawer app v-model="drawer" class="deep-purple lighten-2" dark disable-resize-watcher>
            <v-list>
                <template v-for="(item, index) in items">
                    <v-list-tile :key="index">
                        <v-list-tile-content>
                            {{item.title}}
                        </v-list-tile-content>
                    </v-list-tile>
                    <v-divider :key="`divider-${index}`"></v-divider>
                </template>
            </v-list>
        </v-navigation-drawer>
        <v-toolbar app color="deep-purple darken-1" dark>
            <v-toolbar-side-icon class="hidden-md-and-up" @click="drawer = !drawer"></v-toolbar-side-icon>
            <v-spacer class="hidden-md-and-up"></v-spacer>
            <v-toolbar-title>{{appTitle}}</v-toolbar-title>
            <v-btn flat class="hidden-sm-and-down">Menu</v-btn>
            <v-spacer class="hidden-sm-and-down"></v-spacer>
        </v-toolbar>
    </div>
    
</template>

<style scoped>
</style>
