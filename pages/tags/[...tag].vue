<script setup lang="ts">
import { cleanTrailingSlash } from "~~/utils/cleanTrailingSlash";

const route = useRoute();

const tag = cleanTrailingSlash(
  typeof route.params.tag === "string"
    ? route.params.tag
    : route.params.tag.join("/")
);

const contentQuery = await queryContent()
  .where({ tags: { $contains: [tag] } })
  .find();

useHead({
  title: `Blogs relating to ${tag}`,
});
</script>

<template>
  <v-container>
    <v-row>
      <v-col cols="12" lg="4" md="4" sm="6" v-for="item in contentQuery">
        <blog-card
          :title="item.title ?? ''"
          :description="item.description"
          :path="item._path ?? ''"
          :image="item.imag"
        ></blog-card>
      </v-col>
    </v-row>
  </v-container>
</template>
