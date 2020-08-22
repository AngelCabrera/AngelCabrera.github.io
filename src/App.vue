<template>
  <v-app style="overflow-x: hidden;" id="about">
    <v-app-bar app color="#fff" style="z-index: 999;">
      <div class="d-flex align-center mx-auto">
        <v-avatar class="mr-2">
          <img :src="require('./assets/avatar.png')" alt="Angel Cabrera" />
        </v-avatar>
        <h2>
          Ángel Cabrera
        </h2>
      </div>

      <v-spacer class="d-sm-block d-none"></v-spacer>

      <div class="d-md-block d-none">
        <v-btn href="#about" text>
          <span>Sobre mí</span>
        </v-btn>
        <v-btn href="#projects" text>
          <span>Trabajos</span>
        </v-btn>
        <v-btn href="#certifications" text>
          <span>Certificaciones</span>
        </v-btn>
      </div>
      <v-btn
        href="https://www.workana.com/freelancer/977172e77f701c91d87009219171dbb6"
        target="_blank"
        text
        color="primary"
        :small="$vuetify.breakpoint.name === 'xs'"
      >
        <span class="mr-2">Contacto</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <HelloWorld />
    </v-main>
    <v-footer class="font-weight-medium mt-4" dark>
      <v-col class="text-center" cols="12">
        {{ new Date().getFullYear() }} — <strong>Ángel Cabrera</strong>
      </v-col>
    </v-footer>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'App',

  components: {
    HelloWorld,
  },

  data: () => ({
    //
  }),
  mounted() {},
};
</script>
