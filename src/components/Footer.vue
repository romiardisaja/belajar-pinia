<template>
    Ini Footer
    <br>
    <button @click="increment">Increment+1</button>
    <button @click="decrement">Decrement-1</button>
    <button @click="reset">Reset</button>
</template>

<script setup>
import { useCounterStore } from '../stores/counter'

const counterStore = useCounterStore();
const increment = () => {
    counterStore.$patch((state) => {
        state.count++
    })
}
const decrement = () => {
    counterStore.$patch((state) => {
        state.count--
    })
}
const reset = () => {
    counterStore.$reset();
}
counterStore.$subscribe((mutations, state) => {
    console.log(mutations, state);
})
</script>