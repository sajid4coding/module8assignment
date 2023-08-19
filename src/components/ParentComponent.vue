<script setup>
import { ref } from 'vue'
import ChildComponent from './childComponents/ChildComponent.vue';
import EmitMessage from './childComponents/EmitMessage.vue';

const message = ref('Hi, I am Sajid')

const receivedMessage = ref('');

const displayMessage = (message) => {
  receivedMessage.value = message;
};

</script>
<template>
    <div class="container">
        <div class="card text-start my-5">
          <div class="card-body">
            <span>Parent</span> - <small>{{ message }}</small>
            <input class="form-control my-3" type="text" v-model="message">
            <EmitMessage @messageEmitted="displayMessage"/>
            <p class="mt-2">ChildComponent: {{ receivedMessage }}</p>
          </div>
        </div>
    </div>
    <ChildComponent v-model:msg='message' :messageFromParent='message'/>
</template>


  
