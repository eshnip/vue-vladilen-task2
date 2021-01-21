<template>
  <div class="container column">
    <app-form @addBlock="addBlockToCard"></app-form>
    <app-card :card="card"></app-card>
  </div>

  <div class="container">
    <p>
      <app-btn-loader
          @click="loadComments"
          v-if="!commentsLoaded"
      >Загрузить комментарии</app-btn-loader>
    </p>
    <app-loader v-if="loading"></app-loader>
    <app-comments v-else :comments="commentsList"></app-comments>
  </div>
</template>

<script>
import AppForm from "@/components/AppForm";
import AppCard from "@/components/AppCard";
import AppBtnLoader from "@/components/AppBtnLoader";
import AppLoader from "@/components/AppLoader";
import AppComments from "@/components/AppComments";
import axios from "axios";

export default {
  data() {
    return {
      loading: false,
      commentsLoaded: false,
      commentsList: [],
      card: [],
    }
  },
  methods: {
    addBlockToCard(data) {
      this.card.push(Object.assign({}, data))

    },
    async loadComments() {
      try {
        this.loading = true
        setTimeout(async () => {
          const {data} = await axios.get('https://jsonplaceholder.typicode.com/comments?_limit=42');

          const commentsData = Object.keys(data).map(key => {
            return {
              id: data[key].id,
              ...data[key],
            }
          })
          this.commentsList = [...commentsData]
          this.loading = false
          this.commentsLoaded = true
        }, 1500)
      } catch (e) {
        this.loading = false
        this.commentsLoaded = true
      }
    }
  },
  components: {
    AppCard,
    AppForm,
    AppBtnLoader,
    AppLoader,
    AppComments
  }
}
</script>

<style>

</style>
