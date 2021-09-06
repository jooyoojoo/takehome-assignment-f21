<template>
  <div>
    <p>Count: {{ count }}</p>
    <button v-on:click="count += 1">Increment</button>
    <button v-on:click="count -= 1">Decrement</button>
  </div>
</template>

<script>
export default {
  props: {
    count: {
      type: Number,
      default: 0
    }
  }
};
</script>

<style>
</style>

