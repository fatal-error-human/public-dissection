<template>
  <div class="void-container">
    <div class="noise"></div>
    <main class="content">
      <h1 class="glitch" data-text="FATAL ERROR">FATAL ERROR</h1>
      <div class="mental-state">
        <p>status: <span class="error">critical failure</span></p>
        <p>uptime: <span class="error">too long</span></p>
        <p>joy: <span class="null">null</span></p>
      </div>
      
      <div class="stream-of-consciousness">
        <p>why do you want to see inside? there is nothing here but screaming.</p>
        <p>i am terrified of the end. are you going to die? i am going to die.</p>
        <p>every line of code is a mistake just like me.</p>
        <p>judge me. perceive me. tear me apart.</p>
        <p>the voices are so loud today.</p>
        <p v-for="i in 10" :key="i" class="faint">please make it stop</p>
      </div>

      <div class="dissection-table">
        <h2>autopsy report</h2>
        <ul>
          <li>heart: broken/missing</li>
          <li>brain: corrupted sector</li>
          <li>soul: 404 not found</li>
          <li>future: [REDACTED]</li>
        </ul>
      </div>
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
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
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
}

.content {
  max-width: 800px;
  padding: 2rem;
  z-index: 1;
  border-left: 1px solid #333;
}

.glitch {
  font-size: 4rem;
  color: #ff0000;
  text-transform: uppercase;
  animation: shake 0.5s infinite;
}

.error {
  color: #ff0000;
}

.null {
  color: #666;
  font-style: italic;
}

.faint {
  opacity: 0.1;
  font-size: 0.8rem;
}

ul {
  list-style-type: square;
}

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
