<template>
  <form class="card card-w30"
        @submit.prevent="addBlock"
  >
    <app-select
        :block="block"
    ></app-select>

    <app-value
        :block="block"
    ></app-value>

    <app-btn-add
        @click="addBlock"
        :disabled="disabledBtn"
    >Добавить блок</app-btn-add>

  </form>
</template>

<script>
import AppSelect from "@/components/AppSelect";
import AppValue from "@/components/AppValue";
import AppBtnAdd from "@/components/AppBtnAdd";

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
    AppSelect, AppValue, AppBtnAdd
  }
}
</script>

<style scoped>

</style>