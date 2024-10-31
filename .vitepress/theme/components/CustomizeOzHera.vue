<template>
  <div class="VPOzHera">
    <div class="OzHera-item column">
      <div class="container">
        <div class="OzHera-item-title">{{ ozHeraData?.title }}</div>
        <div class="OzHera-item-content">
          <p>
            {{ ozHeraData?.desc }}
          </p>
        </div>
        <template v-if="ozHeraData.actions" class="actions">
          <template
            v-for="action in ozHeraData.actions"
            :key="action.link"
            class="action"
          >
            <VPButton
              class="OzHera-item-btn"
              tag="a"
              size="medium"
              :theme="action.theme"
              :text="action.text"
              :href="action.link"
            />
          </template>
        </template>
        <!-- <VPButton
          tag="a"
          size="medium"
          :theme="action.theme"
          :text="action.text"
          :href="action.link"
        /> -->
      </div>
    </div>
    <div class="OzHera-item column">
      <div class="container">
        <img :src="ozHeraData?.image.src" :alt="ozHeraData?.alt" />
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import VPButton from "vitepress/dist/client/theme-default/components/VPButton.vue";
const props = defineProps({
  ozHeraData: {
    type: Object,
    deault: () => {},
  },
});
function handleClick() {
  window.location.href = `${window.location.origin}/en/guide/quick-start.html`;
}
</script>
<style scoped>
.VPOzHera {
  position: relative;
}

.container {
  margin: 0 auto;
  max-width: 1152px;
}
.OzHera-item {
  display: inline-block;
  padding-top: 40px;
  line-height: 1.5;
  width: 100%;
}
.OzHera-item:nth-child(1) {
  padding-top: 64px;
}
img {
  box-shadow: 0 8px 16px 0 #0000000d;
  padding-top: 64px;
  margin: 0 auto;
}
.OzHera-item-title {
  color: #50bffe;
  font-size: 48px;
  font-weight: 700;
  margin-bottom: 20px;
  word-break: break-all;
}
.OzHera-item-content {
  color: var(--vp-c-text-1);
  font-size: 24px;
}
.OzHera-item-btn {
  background-color: #5974ce;
  border-radius: 20px;
  padding: 4px 14px;
  width: fit-content;
  color: var(--vp-c-bg-elv);
  margin: 60px 0;
  cursor: pointer;
}
@media (max-width: 640px) {
  .column {
    padding: 0 24px;
  }
  .OzHera-item-title.OzHera-item-title.OzHera-item-title {
    font-size: 36px;
  }
}

@media (min-width: 640px) {
  .column {
    padding: 0 48px;
  }
}
@media (min-width: 960px) {
  .column {
    padding: 0 64px;
  }
}
</style>
