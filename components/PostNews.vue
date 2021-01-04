<template>
  <div class="c-news__list">
    <div class="c-news__box" v-for="content in newsData" :key="content.id">
      <nuxt-link :to="`/news/${content.id}`">
      <div class="date"><time>{{ $moment(content.createdAt).format('YYYY-MM-DD') }}</time></div>
      <h3>{{ content.title }}</h3>
      </nuxt-link>
    <!-- /.c-news__box --></div>
  <!-- /.c-news__list --></div>  
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      posts: [],
    }
  },
  props:['newsData']
}
</script>

<style scoped lang="scss">
.c-news{
  &__list{
    max-width: 980px;
    margin:0 auto smooth_size(45px , 50px);
  }
  &__box{
    padding: 15px 0;
    margin-bottom: 30px;
    border-bottom: 1px solid #ddd;
    a{
      display: flex;
      align-items: center;
      .date{
        margin-right: 20px;
      }
    }
  }
}
</style>
