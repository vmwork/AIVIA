<template>
  <v-app>
    <v-main>
      <Layout></Layout>
      <router-view />
    </v-main>
  </v-app>
</template>

<script lang="ts" setup>
import Layout from "@/layouts/Layout.vue";
</script>
