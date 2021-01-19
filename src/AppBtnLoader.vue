<template>
  <button
      class="btn primary"
      @click="$emit('load')"
  >Загрузить комментарии</button>
</template>

<script>
export default {
  emits: ['load'],
  props: [],
}
</script>

<style scoped>

</style>