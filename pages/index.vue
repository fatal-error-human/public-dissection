<template>
  <div class="page-content">
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
  </div>
</template>
