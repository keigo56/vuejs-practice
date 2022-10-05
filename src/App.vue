<script setup>
import { ref } from 'vue';
const hero_names = ref(['Pudge', 'Void', 'Puck', 'Invoker', 'Ursa']);
</script>

<template>
  <div class="bg-red-700">
    <ul>
      <p v-for="hero_name in hero_names">{{ hero_name }}</p>
    </ul>
  </div>
</template>
