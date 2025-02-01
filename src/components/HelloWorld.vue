<template>
    <v-container class="d-flex flex-column align-center">
        <v-label class="mb-4"><h1>Greetings, Earthling.</h1></v-label>
        <v-btn max-width="200" @click="clicked++">Click me</v-btn>
        <v-label>Clicked: {{ clicked }}</v-label>
        <v-data-table
            :headers="headers"
            :items="items"
            :items-per-page="5"
            :show-select="true"
            :multi-sort="true"
            :footer-props="{
                showFirstLastPage: true,
                itemsPerPageOptions: [5, 10, 25],
                itemsPerPageText: 'Items per page'
            }"
            item-value="id"
            item-disabled="disabled"
            class="elevation-1"
            dense
            outlined
            :loading="loading"
            :search="search"
            must-sort
        >
        </v-data-table>
    </v-container>
</template>

<script setup lang="ts">
import { shallowRef, type ShallowRef } from 'vue';
const clicked: ShallowRef<number> = shallowRef(0);
const headers = [
    { text: 'Name', value: 'name', sortable: true },
    { text: 'Age', value: 'age', sortable: false },
    { text: 'City', value: 'city', sortable: true },
    { text: 'ID', value: 'id', sortable: true }
];
const items = [
    { id: 1, name: 'John Doe', age: 28, city: 'New York' },
    { id: 2, name: 'Jane Smith', age: 34, city: 'Los Angeles' },
    { id: 3, name: 'Sam Johnson', age: 25, city: 'Chicago' }
];
let search = '';
const foo = (x: number) => {
    let y = x == 3;
};
let loading = false;
</script>
