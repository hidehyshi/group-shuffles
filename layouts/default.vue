<script setup lang="ts"></script>
<template>
  <div>
    <header>Nuxt App</header>
    <!-- 下記slotは、NuxtLayoutコンポーネントの子要素に差し代わる -->
    <slot />
    <footer>&copy; ASKUL</footer>
  </div>
</template>
<style>
header {
  background: #000;
  color: #fff;
}
footer {
  background: orange;
  text-align: center;
}
</style>