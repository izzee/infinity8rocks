<template>
  <header class="card">
    <h2>Nuxtlify</h2>
    <nav>
      <nuxt-link to="/" exact>Home</nuxt-link>
      <nuxt-link to="/feed">Feed</nuxt-link>
      <nuxt-link to="/about">About</nuxt-link>
    </nav>
  </header>
</template>

<style scoped lang="scss">
  header {
    padding: 16px;
    display: flex;
    align-items: center;
    line-height: 1;
  }

  nav {
    flex: 1;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    gap: 16px;
  }
</style>