<template>
  <div class="p-kv">
    <div class="c-container">
      <div class="p-kv__copy">Jamstack勉強用のテストブログ</div>
    </div>
  <!-- /.p-kv --></div>
</template>

<script>
export default {
  
}
</script>

<style scoped lang="scss">
.p-kv{
  background: #f5f5f5;
  padding: smooth_size(30px , 50px);
  min-height: 350px;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  &__copy{
    font-size: smooth_size(30px , 34px);
  }
}
/* スマホ
-------------------------------------------------- */
@media only screen and (max-width:$screen-sp) {
  .p-kv{
    padding: smooth_size(40px , 50px) smooth_size(10px , 20px);
    min-height: 250px;
    &__copy{
      font-size: smooth_size(18px , 22px);
    }
  }
}
</style>
