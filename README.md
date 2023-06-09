# Simple vue vite ssg

Sample project to use vite plugin for static site generation

## project requirements

- node 14+

## Project setup

Create a regular vue/vite project

```bash
npm create vite@latest simple-vue-vite-ssg --template vue
cd simple-vue-vite-ssg
npm i -D vite-ssg vue-router @vueuse/head
```

Now [setup vite-ssg](https://github.com/antfu/vite-ssg). In this example we did
the single page setup:

```javascript
// import { createApp } from 'vue'
import { ViteSSG } from 'vite-ssg/single-page'
import './style.css'
import App from './App.vue'

// createApp(App).mount('#app')
export const createApp = ViteSSG(App)

```

Everything else in development mode just works as expected.

## Note on gh-pages publishing

If you decide to use github pages to publish, enable it on project settings and
then select the github action workflow publish.

Then replace the original action with
[build+publish action](.github/workflows/static.yml)
available in this project.

Last but not least important, setup your
[public base path](https://vitejs.dev/guide/build.html#public-base-path)
so your static site has css and js properly loaded.

---

## Vue 3 + Vite

This template should help get you started developing with Vue 3 in Vite.

The template uses Vue 3 `<script setup>` SFCs, check out the
[script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup)
to learn more.

## Recommended IDE Setup

- [VS Code](https://code.visualstudio.com/) +
  [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar)
  (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).
