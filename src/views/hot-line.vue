<template>
  <div class="page">
    <van-nav-bar
      title="欣致国际物流"
      left-arrow
      @click-left="$router.go(-1)"
    />
    <div>
      <van-grid :gutter="10" :column-num="2" class="grid-box">
        <van-grid-item class="item">
          <div class="line">
            上海——广州
          </div>
          <div>
            2500元
          </div>
        </van-grid-item>
        <van-grid-item class="item">
          <div class="line">
            北京——广州
          </div>
          <div>
            2900元
          </div>
        </van-grid-item>
        <van-grid-item class="item">
          <div class="line">
            长沙——广州
          </div>
          <div>
            2500元
          </div>
        </van-grid-item>
        <van-grid-item class="item">
          <div class="line">
            昆明——广州
          </div>
          <div>
            2900元
          </div>
        </van-grid-item>
      </van-grid>
    </div>

    <!--服务案例-->
    <div class="demo">
      <div class="title">———— 服务案例 ————</div>
      <van-grid :gutter="10" :column-num="2" class="grid-box-2">
        <van-grid-item class="item">
          <div class="line">
            上海——广州
          </div>
          <div class="img-box">
            <img src="../assets/logo.png" alt="">
          </div>
          <div class="comment">
            这家公司服务态度很好，速度也快，好评
          </div>
        </van-grid-item>
        <van-grid-item class="item">
          <div class="line">
            广州——北京
          </div>
          <div class="img-box">
            <img src="../assets/logo.png" alt="">
          </div>
          <div class="comment">
            帮朋友托运的车，朋友很满意这次服务
          </div>
        </van-grid-item>
        <van-grid-item class="item">
          <div class="line">
            昆明——北京
          </div>
          <div class="img-box">
            <img src="../assets/logo.png" alt="">
          </div>
          <div class="comment">
            我是做二手车的，长期跟欣致合作，很不错
          </div>
        </van-grid-item>
      </van-grid>
    </div>

  </div>
</template>
<script>
  export default {
    name: 'Home',
    components: {},
  };
</script>
<style lang="stylus" scoped>
  .page
    height calc(100vh)
    overflow auto
    background-color #f1f1f1
  .grid-box
    margin-top 20px
    .item
      text-align center
      .line
        margin-bottom 40px
  .demo
    margin-top 20px
    .title
      line-height 50px
    .grid-box-2
      >>> .van-grid-item__content
        border-radius 10px
      .item
        .img-box
          img
            display block
            max-width 100%
</style>
