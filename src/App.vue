<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <h2>{{ obj }}</h2>
      <h2 @click="firstAction">{{ firstState }}</h2>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Latest Release</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <HelloWorld />
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import { mapState, mapActions } from "vuex";
// mapState
// mapActions
// mapMutations
// mapGetters
export default {
  name: "App",

  components: {
    HelloWorld,
  },

  computed: {
    ...mapState({
      firstState: (state) => state.auth.firstState,
    }),
  },

  data: () => ({
    obj: "Rajvel",
  }),
  methods: {
    ...mapActions(["firstAction"]),
  },
};
</script>
