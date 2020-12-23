<template>
  <header class="l-header">
    <div class="c-container">
      <h1 class="logo">
        <nuxt-link :to="`/`">
          jamstack-blog
        </nuxt-link>
      </h1>
    </div>
  <!-- /.l-header --></header>
  
</template>

<script>
export default {
  
}
</script>

<style scoped lang="scss">
  .l-header{
    background: #111;
    color: #fff;
    padding: smooth_size(15px , 20px);
    a{
      color: #fff;
    }
  }
</style>
