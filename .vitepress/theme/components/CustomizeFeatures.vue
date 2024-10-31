<script setup lang="ts">
import type { DefaultTheme } from "vitepress/theme";

export interface Feature {
  icon?: DefaultTheme.FeatureIcon;
  title: string;
  details: string;
  link?: string;
  linkText?: string;
  rel?: string;
  target?: string;
}

const props = defineProps<{
  features: Feature[];
}>();
</script>

<template>
  <div v-if="features" class="VPfeatures">
    <div class="container">
      <div class="title">{{ features.title }}</div>
      <div class="items">
        <div
          v-for="feature in features.items"
          :key="feature.title"
          class="item"
        >
          <div class="item-img">
            <img :src="feature.icon.src" :alt="feature.icon.alt" />
          </div>
          <div class="item-content">
            <div class="item-content-title">{{ feature.title }}</div>
            <div class="item-content-detail">{{ feature.details }}</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.VPfeatures {
  margin: 64px 0 0 0;
  background-color: var(--vp-c-bg-soft);
}

@media (max-width: 640px) {
  .VPfeatures {
    padding: 0 24px;
  }
}
@media (min-width: 640px) {
  .VPfeatures {
    padding: 0 48px;
  }
}

@media (min-width: 960px) {
  .VPfeatures {
    padding: 0 64px;
  }
}

.container {
  margin: 0 auto;
  max-width: 1152px;
}
.title {
  font-size: 32px;
  font-weight: 600;
  text-align: center;
  padding-bottom: 40px;
  padding-top: 40px;
}
.items {
  display: flex;
  flex-wrap: wrap;
}

.item {
  min-height: 140px;
  box-sizing: border-box;
  padding: 8px 8px 32px 8px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
}

@media (max-width: 640px) {
  .item {
    width: 100%;
  }
}

@media (min-width: 640px) {
  .item {
    width: 50%;
  }
}
.item-img {
  width: 26px;
  margin-right: 30px;
  background-color: #fff;
}
.item-content {
  width: 100%;
  padding-right: 20px;
}
.item-content-title {
  color: var(--vp-c-text-1);
  padding-bottom: 6px;
}
.item-content-detail {
  color: var(--vp-c-text-2);
}
</style>
