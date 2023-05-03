<script setup>
import "../node_modules/bootstrap/js/index.esm.js"
import "../node_modules/bootstrap/dist/css/bootstrap.min.css"
import "../node_modules/bootstrap-icons/font/bootstrap-icons.css"
import { RouterLink, RouterView } from 'vue-router'
import HeaderComponent from './components/HeaderComponent.vue'
import CarrouselComponent from './components/CarrouselComponent.vue'
import FooterComponent from './components/FooterComponent.vue'
</script>

<template>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <header>
    <link rel="stylesheet" href="src/assets/bootstrap.min.css">
    <link rel="stylesheet" href="src/assets/bootstrap.css">
    <link href="https://afeld.github.io/emoji-css/emoji.css" rel="stylesheet">
  </header>

  <HeaderComponent />
  <RouterView />
  <FooterComponent/>
  
</template>

<style scoped>
  body{
    background: #f2f2f2;
  }
</style>