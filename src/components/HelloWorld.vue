<template>
    <v-container class="d-flex flex-column align-center">
        <v-label class="mb-4"><h1>Greetings, Earthling!</h1></v-label>
        <v-btn max-width="200" @click="clicked++">Click me</v-btn>
        <v-label>Clicked: {{ clicked }}</v-label>
    </v-container>
</template>

<script setup lang="ts">
import { shallowRef, type ShallowRef } from 'vue';
const clicked: ShallowRef<number> = shallowRef(0);
let loading = false;
</script>
