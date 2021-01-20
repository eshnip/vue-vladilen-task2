<template>
  <p>
    <button
        class="btn primary"
        @click="$emit('load')"
    ><slot /></button>
  </p>
</template>

<script>
export default {
  emits: ['load'],
  props: [],
}
</script>

<style scoped>

</style>