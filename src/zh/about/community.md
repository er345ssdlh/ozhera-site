---
outline: deep
---

<script setup>
import { ref } from 'vue'
import ContactList from '@theme/components/ContactList.vue'

const contacts = ref([{
//   title: '微信群',
//   imgSrc: '/images/contact/wetcha-qun.png'
// }, {
  title: '微信公众号',
  imgSrc: '/images/contact/gzh.bmp'
}])
</script>

# 社区

## 为 OzHera 做贡献

你如果对OzHera感兴趣并且乐于为社区贡献代码，可以参考[规范指南](/zh/about/spec-guide)。 你有任何疑问或问题，可以到github提[issues](https://github.com/apache/ozhera/issues/new)反馈。

## 联系我们

### 交流群

<ContactList :list="contacts" />
