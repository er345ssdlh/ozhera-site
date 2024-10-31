<script setup lang="ts">
import CustomizeOzHera from "./CustomizeOzHera.vue";
import CustomizeFeatures from "./CustomizeFeatures.vue";
import { useData } from "vitepress";

const { frontmatter } = useData();
</script>

<template>
  <div class="VPHome">
    <CustomizeOzHera
      v-if="frontmatter.ozHera"
      class="CustomizeOzHera"
      :ozHeraData="frontmatter.ozHera"
    />

    <CustomizeFeatures
      v-if="frontmatter.features"
      class="customizeFeatures"
      :features="frontmatter.features"
    />
  </div>
</template>

<style scoped>
@media (min-width: 768px) {
  .VPHome {
    margin-bottom: 128px;
  }
}
</style>
