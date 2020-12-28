<template>
  <v-app>
    <v-app-bar fixed app flat color="blue">
      <v-toolbar-title :class="$style.toolbar_title" v-text="title" />
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      title: 'Vuetify.js',
    }
  },
}
</script>

<style lang="scss" module>
.toolbar_title {
  color: #ffffff;
  font-weight: bold;
}
</style>
