<template>
  <v-app dark>
    <v-navigation-drawer v-model="drawer" fixed app>
      <div class="d-flex flex-column align-center pt-4">
        <v-img contain height="100px" width="100px" src="/logo.png" />
        <h3 class="py-2">Material Admin</h3>
      </div>
      <v-list shaped>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar fixed app color="white">
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
      <v-spacer />
    </v-app-bar>
    <v-main class="position-relative">
      <div class="hero" />
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: true,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Dashboard',
          to: '/dashboard',
        },
        {
          icon: 'mdi-cart-outline',
          title: 'Orders',
          to: '/orders',
        },
      ],
      right: true,
      rightDrawer: false,
      title: 'Material Admin',
    }
  },
}
</script>
