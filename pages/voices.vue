<template>
  <div class="voices-container">
    <div v-for="voice in activeVoices" :key="voice.id" class="voice" :style="voice.style">
      {{ voice.text }}
    </div>
    <div class="center-text">
      they never stop talking
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const phrases = [
  "you are worthless",
  "everyone hates you",
  "give up",
  "die",
  "failure",
  "mistake",
  "empty",
  "alone",
  "broken",
  "it's your fault"
]

const activeVoices = ref([])
let intervalId

function addVoice() {
  const id = Date.now() + Math.random()
  const text = phrases[Math.floor(Math.random() * phrases.length)]
  const x = Math.random() * 90
  const y = Math.random() * 90
  const size = 0.5 + Math.random() * 2
  const duration = 2 + Math.random() * 3

  activeVoices.value.push({
    id,
    text,
    style: {
      left: `${x}%`,
      top: `${y}%`,
      fontSize: `${size}rem`,
      animationDuration: `${duration}s`
    }
  })

  // Cleanup old voices
  if (activeVoices.value.length > 50) {
    activeVoices.value.shift()
  }
}

onMounted(() => {
  intervalId = setInterval(addVoice, 200)
})

onUnmounted(() => {
  clearInterval(intervalId)
})
</script>

<style scoped>
.voices-container {
  position: relative;
  height: 80vh;
  width: 100%;
  overflow: hidden;
}

.center-text {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 2rem;
  color: #fff;
  z-index: 10;
  background: #000;
  padding: 1rem;
}

.voice {
  position: absolute;
  color: #333;
  pointer-events: none;
  animation: float-up linear forwards;
  white-space: nowrap;
}

@keyframes float-up {
  0% { transform: translateY(0); opacity: 0; }
  20% { opacity: 1; }
  80% { opacity: 1; }
  100% { transform: translateY(-100px); opacity: 0; }
}
</style>
