<template>
  <nav>
    <v-app-bar app text>
      <v-app-bar-nav-icon class="grey--text" @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title class="text-uppercase grey--text">
        <span>ini ibu budi</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <v-btn text>
          <span>
            <router-link to="/about">About</router-link>
          </span>
        </v-btn>

        <v-btn text>
          <span>
            <router-link to="/">Home</router-link>
          </span>
        </v-btn>

        <v-btn text>
          <span>
            <router-link to="/spby">SPBy</router-link>
          </span>
        </v-btn>
      </v-toolbar-items>
    </v-app-bar>

    <v-navigation-drawer app v-model="drawer" class="green">
      <v-list>
        <v-list-item nav v-for="link in links" :key="link.text" router :to="link.route">
          <v-list-item-icon>
            <v-icon left class="white--text">{{link.icon}}</v-icon>
          </v-list-item-icon>
          <span>
            <v-list-item-content>
              <v-list-item-title class="white--text">{{link.text}}</v-list-item-title>
            </v-list-item-content>
          </span>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
export default {
  data: () => ({
    drawer: false,
    links: [
      { icon: "home", text: "Home", route: "/" },
      { icon: "email", text: "SPBy", route: "/spby" },
      { icon: "phone", text: "About", route: "/about" }
    ]
  })
};
</script>