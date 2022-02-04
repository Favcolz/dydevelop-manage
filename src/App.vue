<template>
  <v-app>
    <v-system-bar color="primary" dark app height="100">
      <v-btn icon @click="drawer = !drawer">
        <v-icon>mdi-hamburger</v-icon>
      </v-btn>
    </v-system-bar>

    <v-navigation-drawer touchless app fixed v-model="drawer">
      <v-list nav>
        <v-list-item-group v-model="group">
          <v-list-item to="/">
            <v-list-item-icon>
              <v-icon>mdi-home</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Home</v-list-item-title>
          </v-list-item>

          <v-list-item to="/account">
            <v-list-item-icon>
              <v-icon>mdi-account</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Account</v-list-item-title>
          </v-list-item>

          <v-list-item to="/coffee">
            <v-list-item-icon>
              <v-icon>mdi-coffee</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Coffee</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    <v-main style="background-color: #aaa">
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      drawer: true,
    };
  },
};
</script>
