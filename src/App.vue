<template>
  <div>
    <h1>Menggunakan Store</h1>
    <p>Akses count: {{ countStore.count }}</p>
    <p>Akses doubleCount: {{ countStore.doubleCount }}</p>
    <button @click="countStore.increment">+</button><br /><br />

    <h1>Tanpa Store</h1>
    <p>Akses count tanpa store: {{ count }}</p>
    <button @click="increment">+</button>
  </div>
</template>

<script>
import { useCountStore } from './stores/countStore'

export default {
  setup() {
    const countStore = useCountStore()

    function increment() {
      countStore.increment()
    }

    return { countStore, increment }
  }
}
</script>
