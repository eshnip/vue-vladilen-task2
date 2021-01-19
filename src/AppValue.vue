<template>
  <div class="form-control">
    <label for="value">Значение</label>
    <textarea
        id="value"
        rows="3"
        v-model="value"
    ></textarea>
  </div>
</template>

<script>
export default {
  data() {
    return {
      value: ''
    }
  },
  computed: {
    textareaLength() {
      return this.value
      console.log(this.value)
    }
  }
}
</script>

<style scoped>

</style>