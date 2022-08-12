<template>
  <div id="app">
    <Header></Header>
    <List></List>
    <!-- <h1 style="color: white">Pokemon </h1> -->

  </div>
</template>

<script setup>
import Header from './components/Header.vue'
import List from './components/List.vue'
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Lato:wght@400;700&family=Roboto:wght@300;400;500;700&display=swap");

* {
  font-family: "Lato", sans-serif;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

#app {
  width: 100%;
  background: black;
}
</style>
