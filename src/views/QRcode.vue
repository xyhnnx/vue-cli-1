<template>
  <div>
    <van-nav-bar
      title="欣致国际物流"
      left-arrow
      @click-left="$router.go(-1)"
    />
    <div class="box">
      <img class="img" src="../assets/QR.png" alt="">
      <div class="text">
        上海欣致国际物流
      </div>
    </div>
  </div>

</template>

<style lang="stylus">
  .box
    padding-top 50px
    text-align center
    .img
      width 170px
    .text
      margin-top 10px
</style>
