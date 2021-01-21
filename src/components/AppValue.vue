<template>
  <div class="form-control">
    <label for="value">Значение</label>
    <textarea
        id="value"
        rows="3"
        @input="textareaLength"
        v-model="block.text"
    ></textarea>
  </div>
</template>

<script>
export default {
  emits: ['textareaLength'],
  props: ['block'],
  methods: {
    textareaLength() {
      this.$emit('textareaLength', this.block.text)
    }
  },
}
</script>

<style scoped>

</style>