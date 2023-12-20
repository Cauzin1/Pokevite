
<script setup>
  import { ref } from 'vue'

  let num = ref(0)
  </script>

<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
  <div class="container-fluid">
    <router-link class="navbar-brand" to="/">
      <img src="https://www.pokencyclopedia.info/sprites/spin-off/ico_shuffle/ico_shuffle_158.png" alt="Bootstrap" width="30" height="24">
      PokeVite
    </router-link>
    <router-link class="nav- link" to="/">PokeVite</router-link>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <router-link class="nav- link" to="/">Home</router-link>
        </li>
        <li class="nav-item">
         <router-link class="nav- link" to="/about">About</router-link>
        </li>
      </ul>
    </div>
  </div>
</nav>

<!--Content-->
<div class="main">
  <router-view></router-view>
  <footer class="bg-primary text-light">
    <div>
      {{ new Date().getFullYear() }}
    </div>
  </footer>
</div>
</template>

<style>
  footer{
    position: fixed;
    bottom: 0;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 56px;
  }
</style>
