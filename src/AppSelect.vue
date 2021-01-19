<template>
  <div class="form-control">
    <label for="type">Тип блока</label>
    <select id="type" v-model="block">
      <option value="title">Заголовок</option>
      <option value="subtitle">Подзаголовок</option>
      <option value="avatar">Аватар</option>
      <option value="text">Текст</option>
    </select>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>

</style>