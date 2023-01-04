<template>
  <div class="container mx-auto">
    <router-link class="text-xl hover:text-blue-500" to="/">Home</router-link>
    <router-link class="text-xl hover:text-blue-500 ml-4" to="/about"
      >About</router-link
    >
    <hr />
    <br />
    <router-view></router-view>
  </div>
</template>

<style scoped></style>
