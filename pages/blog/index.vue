<script setup lang="ts">
const contentQuery = await queryContent().find();

useHead({
  title: "Blogs",
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
