<template>
<v-app>
    <v-system-bar color="deep-purple darken-3"></v-system-bar>
    <v-app-bar dark app color="deep-purple darken-4">
        <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
        <v-toolbar-title><a href="/" class="white--text" style="text-decoration: none;">Shopping cart</a></v-toolbar-title>

        <div class="flex-grow-1"></div>
        <v-btn class="" text>
            Products
        </v-btn>

        <v-fade-transition mode="out-in">
            <v-btn icon class="mx-2">

                <v-badge overlap right color="indigo">

                    <template v-slot:badge>
                        <span>1</span>
                    </template>

                    <v-icon large>shopping_cart</v-icon>
                </v-badge>

            </v-btn>
        </v-fade-transition>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" absolute temporary>

        <v-list nav shaped>
            <v-list-item-group v-model="nav_group" class="deep-purple--text text--accent-4" active-class="deep-purple--text text--accent-4">
                <v-list-item v-for="(item, index) in items" :key="index" :href="item.href">
                    <v-list-item-icon>
                        <v-icon>{{item.icon}}</v-icon>
                    </v-list-item-icon>

                    <v-list-item-content>
                        <v-list-item-title>{{item.title}}</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
            </v-list-item-group>
        </v-list>

        <v-divider></v-divider>

    </v-navigation-drawer>

    <searchBar></searchBar>

    <v-content>
        <router-view></router-view>
    </v-content>
    <myFooter></myFooter>

</v-app>
</template>

<script>
import searchBar from './components/shared/searchBar';
import myFooter from './components/shared/footer';

export default {
    name: 'App',
    components: {
        searchBar,
        myFooter
    },
    data: () => ({
        //
        component: "homeVue",
        nav_group: null,
        drawer: false,
        icons: [
            'fab fa-facebook',
            'fab fa-twitter',
            'fab fa-google-plus',
            'fab fa-linkedin',
            'fab fa-instagram',
        ],
        items: [{
                icon: "home",
                title: "Home",
                href: "/"
            },
            {
                icon: "settings",
                title: "settings",
                href: "Settings"
            }
        ]
    }),
    watch: {
        nav_group() {
            this.drawer = false;
        }
    }
};
</script>
