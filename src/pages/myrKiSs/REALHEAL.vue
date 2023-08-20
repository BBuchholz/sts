<script setup>
import { useClipboard } from '@vueuse/core'

const sourceContent
= `
---

uuid: goesHere
date: goesHere
time: goesHere
wxrdType: meditation

---

#maloka/healing_relationships

reflections before:

reflections after: 


`

const source = ref(sourceContent)
const { text, copy, copied, isSupported } = useClipboard({ source })
</script>

<template>
  <div v-if="isSupported">
    <button @click="copy(source)">
      <!-- by default, `copied` will be reset in 1.5s -->
      <span v-if="!copied">Copy</span>
      <span v-else>Copied!</span>
    </button>
    <p>
      Current copied: <code>{{ text || 'none' }}</code>
    </p>
  </div>
  <p v-else>
    Your browser does not support Clipboard API
  </p>
  <div>
    <!-- <a href="https://anxious-grove.netlify.app/" target="_blank"> -->
    <img class="card" src="/REALHEAL-73a4.png">
    <!-- </a> -->
  </div>
</template>

<style>
  .card {
    max-width: 50%;
    height: auto;
    display: block;
    margin-left: auto;
    margin-right: auto;
    margin-top: 50px;
    margin-bottom: 50px;
    border: 5px;
    border-color: white;
    border-style: solid;
    border-radius: 1%;
  }
</style>
