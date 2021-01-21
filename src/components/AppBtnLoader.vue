<template>
    <button
        class="btn primary"
        @click="$emit('load')"
    ><slot /></button>
</template>

<script>
export default {
  emits: ['load'],
  props: [],
}
</script>

<style scoped>

</style>