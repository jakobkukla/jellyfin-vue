<template>
  <v-app>
    <v-main>
      <nuxt keep-alive :keep-alive-props="{ max: 10 }" />
    </v-main>
    <v-footer app color="rgba(0, 0, 0, 0)">
      <locale-switcher large top />
    </v-footer>
    <snackbar />
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';
import { mapActions } from 'vuex';

export default Vue.extend({
  beforeMount() {
    this.callAllCallbacks();
  },
  methods: {
    ...mapActions('displayPreferences', ['callAllCallbacks'])
  }
});
</script>
