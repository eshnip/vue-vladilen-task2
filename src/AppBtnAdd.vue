<template>
  <button
      class="btn primary"
      @click.prevent="$emit('addBlock')"
      :disabled="disabled"
  >Добавить</button>
</template>

<script>
export default {
  emits: ['addBlock'],
  props: {
    valueLength: {
      type: String,
      required: true,
    }
  },
  data() {
    return {
      '': ''
    }
  }
}
</script>

<style scoped>

</style>