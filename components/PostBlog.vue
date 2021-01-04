<template>
  <div class="c-blog__list">
    <div class="c-blog__box" v-for="content in blogData" :key="content.id">
      <nuxt-link :to="`/blog/${content.id}`">
      <div class="img"><img :src="content.thumbnail.url" alt=""></div>
      <h3>{{ content.title }}</h3>
      </nuxt-link>
    <!-- /.c-blog__box --></div>
  <!-- /.c-blog__list --></div>  
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      posts: [],
    }
  },
  props:['blogData']
}
</script>

<style scoped lang="scss">
.c-blog{
  &__list{
    display: flex;
    flex-wrap: wrap;
    margin-left: -15px;
    margin-right: -15px;
  }
  &__box{
    width: calc(100% / 3);
    padding: 0 15px;
    margin-bottom: 30px;
    .img{
      margin-bottom: 15px;
    }
  }
}
/* スマホ
-------------------------------------------------- */
@media only screen and (max-width:$screen-sp) {
  .c-blog{
    &__box{
      width: calc(100% / 2);
      h3{
        font-size: smooth_size(14px, 16px );
      }
    }
  }
}
</style>
