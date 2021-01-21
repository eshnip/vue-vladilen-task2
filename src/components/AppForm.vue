<template>
  <form class="card card-w30"
        @submit.prevent="addBlock"
  >
    <form-select
        :block="block"
    ></form-select>

    <form-value
        :block="block"
    ></form-value>

    <form-btn-add
        @click="addBlock"
        :disabled="disabledBtn"
    >Добавить блок</form-btn-add>

  </form>
</template>

<script>
import FormSelect from "@/components/FormSelect";
import FormValue from "@/components/FormValue";
import FormBtnAdd from "@/components/FormBtnAdd";

export default {
  emits: ['addBlock'],
  data() {
    return {
      block: {
        type: 'title',
        text: ''
      },
    }
  },
  methods: {
    addBlock () {
      this.$emit('addBlock', this.block)
      this.block.text = ''
    }
  },
  computed: {
    disabledBtn() {
      const textarea = this.block.text
      return textarea.length < 4
    }
  },
  components: {
    FormSelect, FormValue, FormBtnAdd
  }
}
</script>

<style scoped>

</style>