<template>
<nav class="navbar navbar-light bg-light">
  <div class="container-fluid d-flex justify-content-center ">
    <a class="navbar-brand" href="#">
      <img src="@/assets/logo.png" alt="" width="30" height="24" class="d-inline-block align-text-top">
      Vue.js
    </a>
    <router-link to="/" class="m-2">HOME</router-link>
    <router-link to="/about">USERS</router-link>
  </div>
</nav>
</template>
<style>
a{
  text-decoration: none;
  font-size: 18px;
  text-transform: uppercase;
}
</style>

