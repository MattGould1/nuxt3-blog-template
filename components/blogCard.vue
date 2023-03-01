<script setup lang="ts">
interface Props {
  title: string;
  description: string;
  path: string;
  image?: string;
}
defineProps<Props>();
</script>
<template>
  <v-card>
    <v-card-title>{{ title }}</v-card-title>
    <v-img v-if="image" height="200" :src="image" cover></v-img>
    <v-card-text>{{ description }}</v-card-text>

    <v-card-actions>
      <v-btn :to="`/blog${path}/`">Read More</v-btn>
    </v-card-actions>
  </v-card>
</template>
