<template>
  <div>
    <TheKv />
    <section class="p-index_blog">
      <div class="c-container">
        <h2 class="c-ttl01">
          <span class="en">Blog</span>ブログ
        </h2>
        <div class="p-index_blog__list">
          <div class="p-index_blog__box" v-for="content in contents" :key="content.id">
            <nuxt-link :to="`/blog/${content.id}`">
            <div class="img"><img :src="content.thumbnail.url" alt=""></div>
            <h3>{{ content.title }}</h3>
            </nuxt-link>
          <!-- /.p-index_blog__box --></div>
        <!-- /.p-index_blog__list --></div>
      </div>
    <!-- /.p-index_blog --></section>
  </div>
</template>

<script>
import axios from 'axios'
import TheKv from '@/components/TheKv.vue'
import PostBlog from '@/components/PostBlog.vue'
export default {
  async asyncData() {
    const { data } = await axios.get(
      // your-service-id部分は自分のサービスidに置き換えてください
      'https://ymo.microcms.io/api/v1/blog',
      {
        // your-api-key部分は自分のapi-keyに置き換えてください
        headers: { 'X-API-KEY': '2c5fb001-dea6-450c-9264-be09e811e9e8' }
      }
    )
    return data
  }
}
</script>

<style scoped lang="scss">
.p-index_blog{
  padding: smooth_size(50px , 55px);
  &__list{
    display: flex;
    margin-left: -15px;
    margin-right: -15px;
  }
  &__box{
    width: calc(100% / 3 - 15px);
    padding: 0 15px;
    margin-bottom: 30px;
    .img{
      margin-bottom: 15px;
    }
  }
}
</style>
