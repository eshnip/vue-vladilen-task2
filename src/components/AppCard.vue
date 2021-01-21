<template>
  <div class="card card-w70">
    <h3 v-if="!card.length">Добавьте первую запись, чтобы увидеть результат</h3>

    <template
        v-for="(block, idx) in card"
        :key="idx"
    >
      <component :is="'card-block-' + block.type"
                 :text="block.text"
      ></component>
    </template>



  </div>
</template>

<script>
import CardBlockTitle from "@/components/blocks/CardBlockTitle";
import CardBlockSubtitle from "@/components/blocks/CardBlockSubtitle";
import CardBlockAvatar from "@/components/blocks/CardBlockAvatar";
import CardBlockText from "@/components/blocks/CardBlockText";
export default {
  props: {
    card: Array,
  },
  components: {
    CardBlockTitle, CardBlockSubtitle, CardBlockAvatar, CardBlockText
  }

}
</script>

<style scoped>

</style>