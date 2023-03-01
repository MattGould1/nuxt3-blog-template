<script setup lang="ts">
const router = useRouter();

const icons = ["mdi-github", "mdi-gitlab", "mdi-linkedin"];
</script>

<template>
  <v-app>
    <v-app-bar>
      <template v-slot:image>
        <!-- <v-img
          gradient="to top right, rgba(10, 40, 80,.8), rgba(19,84,122,.8)"
        ></v-img> -->
      </template>

      <v-app-bar-title><v-btn to="/" icon="mdi-home"> </v-btn></v-app-bar-title>

      <v-spacer></v-spacer>

      <v-btn to="/blog/">Blog</v-btn>

      <v-btn to="/what-even-is-this/"> What even is this? </v-btn>
    </v-app-bar>

    <v-main>
      <slot />
    </v-main>

    <v-footer class="text-center d-flex flex-column">
      <div>
        <v-btn
          v-for="icon in icons"
          :key="icon"
          class="mx-4"
          :icon="icon"
          variant="text"
        ></v-btn>
      </div>

      <div class="pt-0">Lorem Ipsum</div>

      <v-divider></v-divider>

      <div>{{ new Date().getFullYear() }} — <strong>Matt Gould</strong></div>
    </v-footer>
  </v-app>
</template>
