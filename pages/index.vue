<template>
  <div>
    <TheKv />
    <section class="p-index_blog">
      <div class="c-container">
        <h2 class="c-ttl01">
          <span class="en">Blog</span>ブログ
        </h2>
        <PostBlog :blogData="blog" />
      </div>
    <!-- /.p-index_blog --></section>
    <section class="p-index_news">
      <div class="c-container">
        <h2 class="c-ttl01">
          <span class="en">News</span>お知らせ
        </h2>
        <PostNews :newsData="news" />
      </div>
    <!-- /.p-index_news --></section>
  </div>
</template>

<script>
import axios from 'axios'
import TheKv from '@/components/TheKv.vue'
import PostBlog from '@/components/PostBlog.vue'
export default {
  async asyncData({ app }) {
    const [blog] = await Promise.all([
      app.$axios.get('https://ymo.microcms.io/api/v1/blog', { headers: {'X-API-KEY': '2c5fb001-dea6-450c-9264-be09e811e9e8'} })
    ])
    const [news] = await Promise.all([
      app.$axios.get('https://ymo.microcms.io/api/v1/news', { headers: {'X-API-KEY': '2c5fb001-dea6-450c-9264-be09e811e9e8'} })
    ])
    return { blog: blog.data.contents ,news: news.data.contents }
  },
}
</script>

<style scoped lang="scss">
.p-index_blog{
  padding: smooth_size(50px , 55px);
}
.p-index_news{
  background: #f5f5f5;
  padding: smooth_size(50px , 55px);
}

/* スマホ
-------------------------------------------------- */
@media only screen and (max-width:$screen-sp) {
  .p-index_blog{
    padding: smooth_size(35px , 40px) smooth_size(15px , 20px);
  }
  .p-index_news{
    padding: smooth_size(35px , 40px) smooth_size(15px , 20px);
  }
}
</style>
