<script setup>
    import { ref } from 'vue'
    defineProps({
        msg: String,
        messageFromParent: String
    })
    defineEmits([
        'update:msg'
    ])
    const newMessage = ref('This is Child Component')
</script>
<template>
    <div class="container">
        <div class="card text-start my-5">
            <div class="card-body">
                <span>Child</span> - <small>{{ msg }}</small>
                <input class="form-control my-3" type="text" :value="msg" @input="$emit('update:msg', $event.target.value)">

                <button @click="msg=newMessage" class="btn btn-primary mx-2">Change</button>
                <button v-if="newMessage==msg ? 'style=display: none;' : ''" @click="msg=messageFromParent" class="btn btn-primary mx-2">Previous</button>
          </div>
        </div>
    </div>
</template>

  
