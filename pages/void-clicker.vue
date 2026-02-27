<template>
  <div class="game-container">
    <h1>futile effort simulator</h1>
    <p>click to fill the void. (spoiler: you can't)</p>
    
    <div class="score-display">
      entropy generated: {{ count }}
    </div>

    <button @click="incrementVoid" class="void-btn" :style="btnStyle">
      {{ btnText }}
    </button>

    <div v-if="message" class="void-message">
      {{ message }}
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const count = ref(0)
const messages = [
  "nothing happened.",
  "still empty.",
  "why are you doing this?",
  "it doesn't matter.",
  "stop it.",
  "you are wasting time.",
  "i am going to die.",
  "the numbers mean nothing.",
  "please leave me alone.",
  "FATAL ERROR"
]

const message = ref('')

const btnText = computed(() => {
  if (count.value > 50) return "STOP"
  if (count.value > 20) return "GIVE UP"
  return "SCREAM"
})

const btnStyle = computed(() => {
  const intensity = Math.min(count.value * 2, 255)
  return {
    transform: `scale(${1 + count.value * 0.01})`,
    borderColor: `rgb(${intensity}, 0, 0)`,
    color: `rgb(${intensity}, ${255 - intensity}, ${255 - intensity})`
  }
})

function incrementVoid() {
  count.value++
  if (Math.random() > 0.7) {
    message.value = messages[Math.floor(Math.random() * messages.length)]
  }
}
</script>

<style scoped>
.game-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 80vh;
  text-align: center;
}

.void-btn {
  margin-top: 2rem;
  padding: 1rem 3rem;
  background: transparent;
  border: 2px solid #333;
  color: #ccc;
  font-family: 'Courier New', monospace;
  font-size: 1.5rem;
  cursor: pointer;
  transition: all 0.1s;
}

.void-btn:active {
  transform: scale(0.95);
}

.void-message {
  margin-top: 2rem;
  color: #ff0000;
  animation: flicker 2s infinite;
}

@keyframes flicker {
  0% { opacity: 1; }
  50% { opacity: 0.2; }
  100% { opacity: 1; }
}
</style>
