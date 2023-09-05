<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>


      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>


  <RouterView />
</template>

<style scoped>
header
{
  line-height: 1.5;
  max-height: 100vh;
}

.logo
{
  display: block;
  margin: 0 auto 2rem;
}

nav
{
  width: 100%;
  font-size: 15px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active
{
  color: var(--color-text);
}

nav a.router-link-exact-active:hover
{
  background-color: grey;
}

nav a
{
  display: inline-block;
  padding: 0 1px;
  border-left: 4px solid var(--color-border);
}

nav a:first-of-type
{
  border: 4px;
}

@media (min-width: 1024px)
{
  header
  {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo
  {
    margin: 0 2px 0 0;
  }

  header .wrapper
  {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav
  {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 4px 0;
    margin-top: 1px;
  }
}
</style>
