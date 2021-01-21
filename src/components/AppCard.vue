<template>
  <div class="card card-w70">
    <h3 v-if="!card.length">Добавьте первую запись, чтобы увидеть результат</h3>

    <template
        v-for="(block, idx) in card"
        :key="idx"
    >
      <component :is="'app-card-block-' + block.type"
                 :text="block.text"
      ></component>
    </template>



  </div>
</template>

<script>
import AppCardBlockTitle from "@/components/blocks/AppCardBlockTitle";
import AppCardBlockSubtitle from "@/components/blocks/AppCardBlockSubtitle";
import AppCardBlockAvatar from "@/components/blocks/AppCardBlockAvatar";
import AppCardBlockText from "@/components/blocks/AppCardBlockText";
export default {
  props: {
    card: Array,
  },
  components: {
    AppCardBlockTitle, AppCardBlockSubtitle, AppCardBlockAvatar, AppCardBlockText
  }

}
</script>

<style scoped>

</style>