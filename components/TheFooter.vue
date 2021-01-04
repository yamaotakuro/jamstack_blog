<template>
  <footer class="l-footer">
    <div class="c-container">
      <div class="l-footer__navi">
        <ul>
          <li>
            <nuxt-link :to="`/`">HOME</nuxt-link>
          </li>
          <li>
            <nuxt-link :to="`/blog`">ブログ</nuxt-link>
          </li>
          <li>
            <nuxt-link :to="`/news`">お知らせ</nuxt-link>
          </li>
        </ul>
      <!-- /.l-footer__navi --></div>
    </div>
  <!-- /.l-footer --></footer>
  
</template>

<script>
export default {
  
}
</script>

<style scoped lang="scss">
  .l-footer{
    background: #111;
    color: #fff;
    padding: smooth_size(15px , 20px);
    a{
      color: #fff;
    }
    &__navi{
      ul{
        display: flex;
        align-items: center;
        
      }
      li{
        margin: 0 15px;
      }
      a{
        position: relative;
        display: block;
        padding-left: 15px;
        &::before{
          content: ">";
          position: absolute;
          left: 0;
          top: 50%;
          transform: translateY(-50%);
          color: #fff;
        }
      }
    }
  }
</style>
