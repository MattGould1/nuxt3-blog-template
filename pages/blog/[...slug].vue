<script setup lang="ts">
import { cleanTrailingSlash } from "~~/utils/cleanTrailingSlash";

const route = useRoute();
const router = useRouter();

const path = cleanTrailingSlash(
  typeof route.params.slug === "string"
    ? route.params.slug
    : route.params.slug.join("/")
);

const contentQuery = await queryContent()
  .where({ _path: { $eq: `/${path}` } })
  .findOne();

useHead({
  title: contentQuery.title,
});
</script>

<template>
  <main class="blog">
    <v-container>
      <ContentDoc :path="path" />

      <v-row>
        <v-col cols="12">
          <h3 class="mb-2">Read more about similar things :)</h3>
          <NuxtLink
            :to="`/tags/${tag}/`"
            class="mr-2"
            v-for="tag in contentQuery.tags"
            :key="tag"
          >
            {{ tag }}
          </NuxtLink>
        </v-col>
      </v-row>
    </v-container>
  </main>
</template>

<style>
.blog a {
  color: white;
}
.blog p {
  margin-bottom: 16px;
}
</style>
