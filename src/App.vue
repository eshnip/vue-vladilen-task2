<template>
  <div class="container column">
    <form class="card card-w30">
      <app-select></app-select>

      <app-value></app-value>

      <app-btn-add></app-btn-add>
    </form>

    <div class="card card-w70">
      <h1>Резюме Nickname</h1>
      <div class="avatar">
        <img src="https://cdn.dribbble.com/users/5592443/screenshots/14279501/drbl_pop_r_m_rick_4x.png">
      </div>
      <h2>Опыт работы</h2>
      <p>
        главный герой американского мультсериала «Рик и Морти», гениальный учёный, изобретатель, атеист (хотя в некоторых сериях он даже молится Богу, однако, каждый раз после чудесного спасения ссылается на удачу и вновь отвергает его существование), алкоголик, социопат, дедушка Морти. На момент начала третьего сезона ему 70 лет[1]. Рик боится пиратов, а его главной слабостью является некий - "Санчезиум". Исходя из того, что существует неограниченное количество вселенных, существует неограниченное количество Риков, герой сериала предположительно принадлежит к измерению С-137. В серии комикcов Рик относится к измерению C-132, а в игре «Pocket Mortys» — к измерению C-123[2]. Прототипом Рика Санчеза является Эмметт Браун, герой кинотрилогии «Назад в будущее»[3].
      </p>
      <h3>Добавьте первый блок, чтобы увидеть результат</h3>
    </div>
  </div>
  <div class="container">
    <p>
      <app-btn-loader @click="loadComments" v-if="!commentsLoaded"></app-btn-loader>
    </p>

    <app-loader v-if="loading"></app-loader>

    <app-comments v-else :comments="commentsList"></app-comments>
  </div>
</template>

<script>
import AppLoader from "@/AppLoader";
import AppComments from "@/AppComments";
import AppBtnLoader from "@/AppBtnLoader";
import AppSelect from "@/AppSelect";
import AppValue from "@/AppValue";
import AppBtnAdd from "@/AppBtnAdd";
import axios from "axios";

export default {
  data() {
    return {
      loading: false,
      commentsLoaded: false,
      commentsList: [],
      block: 'title'
    }
  },
  methods: {
    addBlock() {

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
    AppLoader, AppComments, AppBtnLoader, AppSelect, AppValue, AppBtnAdd
  }
}
</script>

<style>
  .avatar {
    display: flex;
    justify-content: center;
  }

  .avatar img {
    width: 150px;
    height: auto;
    border-radius: 50%;
  }
</style>
