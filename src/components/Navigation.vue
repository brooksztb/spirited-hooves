<script>
export default {
  name: 'Navigation',
  data() {
    return {
      appTitle: 'Spirited Hooves',
      drawer: false,
      items: [
          { title: 'About',
            link: '#AboutUs' }, 
          { title: 'Services', 
            link: '#Services' }, 
          { title: 'Contact', 
            link: '#ContactForm' }
        ]
    };
  }
};
</script>

<template>
    <div>   
        <v-navigation-drawer app v-model="drawer" class="deep-purple darken-1" dark disable-resize-watcher>
            <v-list>
                <template v-for="(item, index) in items">
                    <v-list-tile :key="index">
                        <v-list-tile-content class="drawer-item" v-scroll-to="item.link" @click="drawer = !drawer">
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
            <v-toolbar-title class="nav-logo-container" v-scroll-to="'#app'">
                <img class="nav-logo hidden-xs-only" src="@/assets/SpiritedHooves-logo.svg" alt="" />
                {{appTitle}}
            </v-toolbar-title>
            <template v-for="(item, index) in items">
                <v-btn flat class="hidden-sm-and-down" v-scroll-to="item.link" :key="index">{{item.title}}</v-btn>
            </template>
            <v-spacer class="hidden-sm-and-down"></v-spacer> 
        </v-toolbar>
    </div>
    
</template>

<style scoped>
    a {
        color: white;
        text-decoration: none;
    }

    .drawer-item {
        cursor: pointer;
    }

    .nav-logo-container {
        cursor: pointer;
    }

    .nav-logo {
        width: 75px;
        height: 75px;
        vertical-align: middle;
    }
</style>
