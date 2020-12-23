<template>
  <div>
    <article class="p-blog">
      <div class="c-container">
        <div class="p-blog__body">  
          <h1 class="blog_ttl">{{ title }}</h1>
          <div class="date"><time>{{ this.$moment(publishedAt).format('YYYY-MM-DD') }}</time></div>
          <div class="post" v-html="body"></div>
        <!-- /.p-blog__body --></div>
      </div>
    <!-- /.p-blog --></article>
    
  </div>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData({ params }) {
    const { data } = await axios.get(
      `https://ymo.microcms.io/api/v1/blog/${params.slug}`,
      {
        headers: { 'X-API-KEY': '2c5fb001-dea6-450c-9264-be09e811e9e8' }
      }
    )
    return data
  }
}
</script>

<style scoped lang="scss">
  .p-blog{
    padding: smooth_size(50px , 55px) 0;
    &__body{
      .blog_ttl{
        font-size: smooth_size(30px , 34px);
        color: #111;
        margin-bottom: 10px;
      }
      .date{
        font-size: smooth_size(16px , 20px);
        border-bottom: 1px solid #ccc;
        padding-bottom: 20px;
        margin-bottom: 30px;
      }
      .post{
        padding: 20px;
        p{
          margin-bottom: 20px;
        }
      }
    }
  }
</style>
