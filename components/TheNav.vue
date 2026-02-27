<template>
  <nav class="nav-bar">
    <NuxtLink to="/" class="nav-link">agony</NuxtLink>
    <NuxtLink to="/voices" class="nav-link">the_chorus</NuxtLink>
    <NuxtLink to="/void-clicker" class="nav-link">futile_effort</NuxtLink>
  </nav>
</template>

<style scoped>
.nav-bar {
  position: fixed;
  top: 0;
  width: 100%;
  display: flex;
  justify-content: center;
  gap: 2rem;
  padding: 1rem;
  background: rgba(0, 0, 0, 0.8);
  border-bottom: 1px solid #333;
  z-index: 100;
  backdrop-filter: blur(5px);
}

.nav-link {
  color: #666;
  text-decoration: none;
  font-family: 'Courier New', monospace;
  font-size: 1.2rem;
  transition: all 0.3s ease;
}

.nav-link:hover {
  color: #ff0000;
  text-shadow: 2px 2px 0px rgba(255, 0, 0, 0.5);
  transform: scale(1.1);
}

.router-link-active {
  color: #fff;
  border-bottom: 1px solid #ff0000;
}
</style>
