<template>
  <button class="btn" :class="color" @click="$emit('makeFirst')">
    <slot />
  </button>
<!--  <button class="btn" :class="color" @click="$emit('makeLast')">last</button>-->
<!--  <button class="btn" :class="color" @click="$emit('upBlock')">+</button>-->
<!--  <button class="btn" :class="color" @click="$emit('downBlock')">-</button>-->
<!--  <button class="btn" :class="color" @click="$emit('removeBlock')">х</button>-->
</template>

<script>
export default {
  emits: ['makeFirst', 'makeLast', 'upBlock', 'downBlock', 'removeBlock'],
  props: {
    color: {
      type: String,
      default: '',
      validator(value) {
        return ['', 'primary', 'danger', 'green', 'blue'].includes(value)
      }
    }
  }
}
</script>

<style scoped>

</style>