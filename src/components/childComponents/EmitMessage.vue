<!-- ChildComponent.vue -->
<template>
    <div>
      <button class="btn btn-warning" @click="emitMessage">Emit Message</button>
    </div>
  </template>
  
  <script setup>
  import { defineProps, defineEmits } from 'vue';
  
  const emit = defineEmits();
  const props = defineProps();
  
  const emitMessage = () => {
    const message = 'Hello from ChildComponent!';
    emit('messageEmitted', message);
  };
  </script>
  

  
