<template>
    <span>
        <v-navigation-drawer
            app
            v-model="drawer"
            class="brown lighten-2"
            dark
            disable-resize-watcher
        >
            <v-list>
                <template v-for="(item, index) in items">
                    <v-list-tile :key="index">
                        <v-list-tile-content>
                            {{ item.title }}
                        </v-list-tile-content>
                    </v-list-tile>
                    <v-divider :key="`divider-${index}`"></v-divider>
                </template>
            </v-list>
        </v-navigation-drawer>
        <v-toolbar app color="brown darken-4" dark>
            <v-toolbar-side-icon
                class="hidden-md-and-up"
                @click="drawer = !drawer"
            >
                <v-icon>menu</v-icon>
            </v-toolbar-side-icon>
            <v-spacer class="hidden-md-and-up"></v-spacer>
            <router-link to="/">
                <v-toolbar-title to="/">{{ appTitle }}</v-toolbar-title>
            </router-link>
            <v-btn
                depressed
                color="brown darken-4"
                class="hidden-sm-and-down"
                to="/menu"
                >Menu</v-btn
            >
            <v-spacer class="hidden-sm-and-down"></v-spacer>
            <v-btn
                depressed
                color="brown darken-4"
                class="hidden-sm-and-down"
                to="/sign-in"
                >SIGN IN</v-btn
            >
            <v-btn color="brown lighten-3" class="hidden-sm-and-down" to="/join"
                >JOIN</v-btn
            >
        </v-toolbar>
    </span>
</template>
<script>
export default {
    name: 'AppNavigation',
    data() {
        return {
            appTitle: 'Meal Prep',
            drawer: false,
            items: [
                { title: 'Menu' },
                { title: 'Profile' },
                { title: 'Sign In' },
                { title: 'Join' }
            ]
        };
    }
};
</script>

<style scoped>
.v-application a {
    color: white;
    text-decoration: none;
}
</style>
