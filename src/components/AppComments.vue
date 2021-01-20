<template>
  <div class="card" v-if="comments.length">
    <h2>{{ commentsTitle }}</h2>
    <ul class="list">
      <li class="list-item"
          v-for="item in comments"
          :key="item.id">
        <div>
          <p><strong>{{ item.email }}</strong></p>
          <small>{{ item.body }}</small>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    comments: Array,
    required: false,
  },
  data() {
    return {
      commentsTitle: 'Комментарии',
    }
  },

}
</script>

<style scoped>

</style>