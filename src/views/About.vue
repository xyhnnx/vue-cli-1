<template>
  <div>
    <van-nav-bar
      title="企业资质"
      left-arrow
      @click-left="$router.go(-1)"
    />
    <div class="about">
      <img src="../assets/company4.png" alt="">
      <img src="../assets/company3.png" alt="">
      <img src="../assets/company2.png" alt="">
      <img src="../assets/company1.png" alt="">
    </div>
  </div>

</template>
<style scoped lang="stylus">
  .about
    text-align center
    img
      max-width 100%
</style>
