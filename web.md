# 📘 Pasar Al-Huda Web — Technical Documentation

A modern, modular, and maintainable Nuxt 3 (TypeScript) application for Pasar Al-Huda.

---

## 📦 Tech Stack Overview

| Area             | Technology            |
|------------------|------------------------|
| Framework        | **Nuxt 3** (TypeScript) |
| Package Manager  | **pnpm**               |
| UI Library       | **Vuetify 3**          |
| Deployment       | **pm2**                |
| HTTP Client      | **Axios** (with interceptor) |
| State Management | **Pinia**              |
| Styling          | **SCSS**               |
| Icons            | **Iconify**            |

---

## 🚀 Development Workflow

1. 🧱 **Clone Nuxt 3 Starter** from [`https://github.com/hasansas/nuxt3-starter-kit`](https://github.com/hasansas/nuxt3-starter-kit) or create from scratch with `npx nuxi init app-name`.
2. 📸 **Screenshot** existing design (each page/component).
3. 🤖 **Ask AI** to generate Vuetify component (strictly avoid inline styles).
4. 🧩 **Implement** component into Nuxt project.
5. 🔌 **Add logic** using composables, Pinia, and API integrations.
6. ✅ Test the 4 UI states: Loading, Error, Data, Empty.

---

## 🧱 Project Structure & Best Practices

### 📁 Directory & Structure

- `/pages`: All route-based pages.
- `/components`: UI blocks reused across pages.
- `/layouts`: Common layout structures.
- `/middleware`: Global & route-specific authentication.
- `/store`: Global store using **Pinia**.
- `/composables`: Reusable logic hooks.
- `/utils`: Helper functions.
- `/assets/styles`: All SCSS files.

---

## 🎨 Styling Guidelines

- Global style entry: `main.scss`
- Place styles in: `/assets/styles`
- **Do not use inline styles**

### ✅ SCSS Structure

| File                | Purpose                       |
|---------------------|-------------------------------|
| `_variables.scss`   | SCSS variables (e.g., colors) |
| `_mixins.scss`      | SCSS mixins for reuse         |
| `main.scss`         | Global styles, reset, Vuetify override |

---

## 🧩 Component Structure

### Order of Blocks
```vue
<template>
<script setup lang="ts">
<style lang="scss" scoped>
```

### Page Data Display Convention

If a page fetches API data, always handle 4 states:

1. ✅ Loading — Use Vuetify Skeleton
2. ❌ Error — Show fallback
3. 📦 Data — Show content
4. 🚫 Empty — Show placeholder

---

## ✍️ Comments & Documentation

### 💡 Code Comments

#### General
- Use `/** ... */` (JSDoc) for:
  - Public functions
  - Types & interfaces

- Use `// ...` for inline/block logic comments.

#### Styling
Use comment headers for sections:

```scss
// ===============================
// Typography & Global Reset
// ===============================
```

Use `// ...` for variables, mixins, and class notes.

---

## 🧾 Naming Conventions

| Type         | Convention         | Example                    |
|--------------|--------------------|----------------------------|
| Variable     | `camelCase`        | `chartData`                |
| Function     | `camelCase`        | `fetchUserSession()`       |
| Logic Func   | `handleCamelCase`  | `handleSubmitForm()`       |
| Composable   | `useCamelCase`     | `useAuth()`                |
| Utils        | `camelCase`        | `formatDate()`             |
| Pages        | `kebab-case.vue`   | `user-dashboard.vue`       |

---

## 🔐 Authentication

- Use `middleware` to protect routes
- Add `auth.global.ts` for global protection
- Use `definePageMeta({ middleware })` in page files

---

## 📡 API Integration

- Use `Axios` with global interceptor
- Wrap API logic inside composables (e.g. `useApi`)
- Standardize API response structure:
  ```ts
  { success: boolean, code: number, data?: any, error?: any }
  ```

---

## 🧹 Code Quality

- **ESLint** for linting (`.eslintrc`)
- **Prettier** for formatting
- Always use simplified block comments for maintainability
