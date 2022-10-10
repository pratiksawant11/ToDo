<template>
  <v-app id="inspire">
    <v-navigation-drawer style="background-color:black" v-model="drawer" class app>
      <v-list-item style="background-color:black">
        <v-list-item-content>
          <v-list-item-title style="color:whitesmoke" class="title">Vuetify Todo</v-list-item-title>
          <v-list-item-subtitle style="color:whitesmoke">Best Todo Ever!</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
      <hr class="white" />
      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item
          style="color:whitesmoke"
          v-for="item in items"
          :key="item.title"
          :to="item.to"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app color="primary" dark src="mp.webp" prominent>
      <template v-slot:img="{ props }">
        <v-img v-bind="props" gradient="to top right, rgba(19,84,122,.5), rgba(128,208,199,.8)"></v-img>
      </template>

      <v-app-bar-nav-icon style="color:black" @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title style="color:black"></v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon style="color:black">
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon style="color:black">
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon style="color:black">
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>
<script>
export default {
  data: () => ({
    drawer: null,
    items: [
      { title: "Todo", icon: "mdi-format-list-checks", to: "/" },
      { title: "About", icon: "mdi-help-box", to: "/about" }
    ]
  })
};
</script>