<script setup lang="ts">
import { ref } from 'vue'

const seconds = ref(0)
const minutes = ref(0)
const interval = ref(null)

function playPause() {
  const next = () => {
    if (seconds.value < 59) {
      seconds.value++
    } else {
      seconds.value = 0
      minutes.value++
    }
  };
  if (interval.value) {
    clearInterval(interval.value)
    interval.value = null
  } else {
    seconds.value = 0
    minutes.value = 0
    interval.value = setInterval(() => {
      next();
    }, 1000)
  }
}
</script>

<template>
  <div flex="~" w="min" border="~ gray-400 opacity-50 rounded-md">
    <span m="auto" p="2"><strong>
      {{ minutes }}:{{ `0${seconds}`.slice(-2) }}
    </strong></span>
    <button
      border="l gray-400 opacity-50"
      font="mono"
      outline="!none"
      hover:bg="gray-400 opacity-20"
      @click="playPause"
    >
      {{ interval ? 'STOP': 'GO!' }}
    </button>
  </div>
</template>

<style scoped>
  span, button {
    width: 110px;
    padding: 14px 16px 11px;
    font-size: 26px;
  }
  span {
    text-align: right;
  }
</style>