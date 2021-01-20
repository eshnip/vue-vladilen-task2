<template>
  <div class="card card-w70">
    <h3 v-if="!card.length">Добавьте первую запись</h3>

    <app-card-block
        v-for="block in card"
        :key="block.id"
        :id="block.id"
        :type="block.type"
        :text="block.text"
    ></app-card-block>

  </div>
</template>

<script>
import AppCardBlock from "@/components/AppCardBlock";
export default {
  props: ['card'],
  components: {
    AppCardBlock
  }

}
</script>

<style scoped>

</style>