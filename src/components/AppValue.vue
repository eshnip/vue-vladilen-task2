<template>
  <div class="form-control">
    <label for="value">Значение</label>
    <textarea
        id="value"
        rows="3"
        v-model="block.text"
    ></textarea>
  </div>
</template>

<script>
export default {
  props: ['block'],
  data() {
    return {
      value: ''
    }
  },
  methods: {

  }
}
</script>

<style scoped>

</style>