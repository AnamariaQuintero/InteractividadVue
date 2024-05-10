<script setup>
import { ref } from 'vue'

const users = ["Anamaria", "Samuel", "Yuliana", "Alejandro"]

const isChecked = ref();
</script>

<template>
    <ul>
        <li v-for="(user, index) in users" :key="index">{{ index }} {{ user }}</li>
    </ul>

    <input type="checkbox" id="check" v-model="isChecked"/>
    <label for="check">Pinchame.</label>
    <div class="bg-purple-300 text-white rounded-full py-1 px-2 w-40"
        :class="{ 'bg-purple-600':isChecked }"
    >
        Este es un mensaje
    </div>
    <div v-show="isChecked">
        Este es un mensaje que podria desaparecer 
    </div>
    <div v-if="isChecked"> 
        Este es un mensaje que podria desaparecer 
    </div>
    <div v-else> 
        Esto se ve porque no cumplio la condicion del if
    </div>

</template>