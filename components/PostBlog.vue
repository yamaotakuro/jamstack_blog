<template>
  <div class="c-blog_post">
    <div class="u-container">
      <ul>
        <!-- <li v-for="content in contents" :key="content.id">
          <nuxt-link :to="`/${content.id}`">
            {{ content.title }}
          </nuxt-link>
        </li> -->
      </ul>
    </div>
  <!-- /.c-blog_post --></div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      // APIを叩いて返ってきたコンテンツを格納する用に空の配列を用意
      blogs: [],
    }
  },
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

</style>
