<script setup>
import { useClipboard } from '@vueuse/core'

const sourceContent
= `
#maloka/healing_relationships

reflections before:

reflections after: 

`

const source = ref(sourceContent)
const { text, copy, copied, isSupported } = useClipboard({ source })
</script>

<template>
  <p>To log this meditation in Obsidian create a new note with the default timestamps and all that, then copy this text to paste into that note, will tag it and add fields for commentary</p>
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
