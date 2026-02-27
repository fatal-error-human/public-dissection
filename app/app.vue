<template>
  <div class="void-container">
    <div class="noise"></div>
    <TheNav />
    <main class="content-wrapper">
      <NuxtPage />
    </main>
  </div>
</template>

<style>
body {
  margin: 0;
  background-color: #000;
  color: #ccc;
  font-family: 'Courier New', monospace;
  overflow-x: hidden;
}

.void-container {
  min-height: 100vh;
  position: relative;
}

.content-wrapper {
  padding-top: 80px; /* Space for nav */
  max-width: 1000px;
  margin: 0 auto;
  padding-left: 1rem;
  padding-right: 1rem;
  z-index: 1;
  position: relative;
}

.noise {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 0.05;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.65' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)'/%3E%3C/svg%3E");
  pointer-events: none;
  z-index: 0;
}

.glitch {
  font-size: 4rem;
  color: #ff0000;
  text-transform: uppercase;
  animation: shake 0.5s infinite;
}

.error { color: #ff0000; }
.null { color: #666; font-style: italic; }
.faint { opacity: 0.1; font-size: 0.8rem; }
ul { list-style-type: square; }

@keyframes shake {
  0% { transform: translate(1px, 1px) rotate(0deg); }
  10% { transform: translate(-1px, -2px) rotate(-1deg); }
  20% { transform: translate(-3px, 0px) rotate(1deg); }
  30% { transform: translate(3px, 2px) rotate(0deg); }
  40% { transform: translate(1px, -1px) rotate(1deg); }
  50% { transform: translate(-1px, 2px) rotate(-1deg); }
  60% { transform: translate(-3px, 1px) rotate(0deg); }
  70% { transform: translate(3px, 1px) rotate(-1deg); }
  80% { transform: translate(-1px, -1px) rotate(1deg); }
  90% { transform: translate(1px, 2px) rotate(0deg); }
  100% { transform: translate(1px, -2px) rotate(-1deg); }
}
</style>
