<template>
  <header>
    <nav class="navbar">
      <RouterLink to='/'><a>Dog</a></RouterLink>
      <RouterLink to='/about'><a>About</a></RouterLink>
    </nav>
  </header>
  <main>
    <RouterView />
  </main>
</template>

<script>
import { RouterLink, RouterView } from 'vue-router'
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: center;
  font-size: 1.5em;
  font-weight: bold;
  margin-bottom: 1.2em;
}

a {
  padding: 10px;
  text-decoration: none;
  color: rgb(81, 90, 110)
}
a.router-link-active {
  text-decoration: underline;
  padding: 10px;
}

</style>
