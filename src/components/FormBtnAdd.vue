<template>
  <button
      type="submit"
      class="btn primary"
      @click.prevent="$emit('addBlock')"
  >
    <slot />
  </button>
</template>

<script>
export default {
  emits: ['addBlock'],
  props: {
    disabledBtn: {
      type: Boolean,
      required: false,
      default: false
    }
  }
}
</script>

<style scoped>

</style>