<script setup>
import { defineClientComponent } from 'vitepress'

const RedirectHome = defineClientComponent(() => {
  return import('@theme/components/RedirectHome.vue')
})
</script>

<RedirectHome />
