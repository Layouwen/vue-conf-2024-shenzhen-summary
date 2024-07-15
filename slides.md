---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: Vue Conf 2024 深圳
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# https://sli.dev/guide/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/guide/syntax#mdc-syntax
mdc: true
---

# Vue Conf 2024 深圳  

大会部分内容摘要

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/layouwen" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: fade-out
---

# 会议主题总览

- **数据加载器** - Eduardo 
- **Vue DevTools Next** - Arlo
- **深入理解单文件组件编译** - 赵锦江
- **TinyVue** - 莫春辉
- **Vue Vapor** - 智子
- **Vue Mini** - 杨明山
- **基于 Vue 开发鸿蒙App** - 辛宝
- **主题演讲** - 尤雨溪

<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/guide/syntax#embedded-styles
-->

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Here is another comment.
-->

---
transition: slide-up
layout: two-cols
---

# 数据加载器

```vue
<script lang="ts">
import { getUserById } from '../api'

export const useUserData = defineLoader(async (route) => {
  // 用于获取的所有内容都应该在 URL 中
  const user = await getUserById(route.params.id)
  return user
})
</script>

<script lang="ts" setup>
  const {
  data: user, // 👆 `user`
  isLoading, // true/false
  error,
  reload, // 手动刷新 ⚡️
} = useUserData()
</script>
```

::right::

- 与 router 相关联
- 支持阻塞/非阻塞模式
- 与 pinia 相关联
- 控制拦截跳转
- 错误阻止跳转
- 请求相关状态收集


```
react/vue-query / alova
react router 中的 loader 函数
```

---
transition: slide-up
layout: two-cols
---

# Vue Devtools Next

```ts
import vue from '@vitejs/pluginvue'
import vueDevTools from 'vitepluginvuedevtools'
export default defneConfg({
  plugins: [
    vue(),
    vueDevTools(),
  ]
})
```

::right::

- 应用内嵌
- 数据统计(Vue版本/页面数量/组件数量)
- 组件查看器(节点树/数据状态/依赖视图)
- 路由导航器(路由列表/导航能力)
- Vue Router 检查器(Routes/Timeline)
- Pinia 检查器
- i18n 检查器
- 资源管理器(资源列表/文件信息)
- 模块依赖图(引用/依赖关系)
- Birpc 通信, 支持多端调试(Electron/Chrome DevTools/独立窗口等)
- 插件 API 支持

---

# 深入理解单文件组件编译

## Bit 组件化开发平台

- 随时从 Bit Cloud 任选若干个组件
- 导入本地化联调, 并支持重新发布
- 每个组件可以单独发布 npm 包供他人使用

---

# TinyVue

一套代码支持 Vue2/3 & PC/手机

<img src="/assets/TinyVue.png">

---
transition: slide-up
layout: two-cols
---

# Vue Vapor

```ts
import { effect, ref } from '@vue/reactivity'
// 初始化
const container = document.createElement('div')
const label = document.createElement('h1')
const button = document.createElement('button')
button.textContent = 'Increase'
button.addEventListener('click', increase) // 注册事件
const count = ref(0)
effect(() => {
  label.textContent = `Count: ${count.value}`
})
function increase() {
  count.value++
}
document.body.append(container)
container.append(label, button)
```

::right::

- 脱离 vDOM
- 更高性能
- 更小体积
- 无痛过度(Vue Vapor 是 Vue vDOM 子集)
- 支持目前几乎所有 vDOM 模式实现的库
- 支持 JSX/TSX
- 不支持 Vue2

---
transition: slide-up
layout: two-cols
---

# Vue Mini

- 基于 Vue3 思路实现的轻量级框架
- 性能接近原生小程序
- 支持 Vue3 所有 Api
- 支持 Composition API
- 还在快速迭代中...

---
transition: slide-up
layout: two-cols
---

# 基于 Vue 开发鸿蒙App

- uts 语言(ts 的超集)
- 产物为纯 Kotlin, 没有 js 引擎
- 支持 Options/Composition

<img src="/assets/UniAppX-01.png">

::right::

<img src="/assets/UniAppX-02.png">

<img src="/assets/UniAppX-03.png">

---
transition: slide-up
---

# 存量 UniApp 鸿蒙适配

<img src="/assets/UniAppX-04.png">

---
transition: slide-up
---

# UniAppX 开发鸿蒙 App

<img src="/assets/UniAppX-05.png">

---

# 面向未来的 Vue 和 Vite

<img src="/assets/Evan-01.png">

---

# Rolldown

<img src="/assets/Evan-02.png">

---

# OXC

<img src="/assets/Evan-03.png">

---
layout: center
class: text-center
---

# Thanks

[https://github.com/layouwen](https://github.com/layouwen)
