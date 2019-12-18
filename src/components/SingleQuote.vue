<template>
  <div class="message" @click="$emit('removeQuote')">
  <div class="message-body">
    <slot></slot>
  </div>
</div>
</template>

<script>
export default {
  props: ['quote']
}
</script>

<style>
.message {
  margin: 1rem;
}
</style>