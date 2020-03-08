<template>
  <div>
    <!--顶部-->
    <van-nav-bar>
      <div slot="title">
        <van-icon name="service-o" />
        {{phone}}
      </div>
      <div slot="right">
        <a :href="`tel:${phone}`" id="phone">
          <van-icon class="phone" name="phone" />
        </a>
      </div>
    </van-nav-bar>

    <!--banner图-->
    <van-swipe class="my-swipe" :autoplay="3000" indicator-color="white">
      <van-swipe-item class="s-item">
      </van-swipe-item>
      <van-swipe-item class="s-item">
        <img class="img" src="../assets/banner1.png" alt="">
      </van-swipe-item>
    </van-swipe>


    <div class="grid-box">
      <van-grid>
        <van-grid-item @click.native="gridClick('/About')" icon="photo-o" text="企业资质" />
        <van-grid-item @click.native="gridClick('/hot-line')" icon="photo-o" text="热门路线" />
        <van-grid-item @click.native="gridClick('/hot-line')" icon="photo-o" text="订单展示" />
        <van-grid-item @click.native="gridClick('')" icon="photo-o" text="查询报价" />
      </van-grid>
    </div>

    <div>
      <!--地区选择-->
      <div class="area-select">
        <div class="area-item">
          <div class="label">出发地</div>
          <div class="value" @click="selectArea(1)">
            <template v-if="startList && startList.length">
              {{startList.map(e=>e.name).join('/')}}
            </template>
            <template v-else>请选择</template>
          </div>
        </div>
        <div class="center" @click="changeArea">
          <van-icon name="exchange" />
        </div>
        <div class="area-item" >
          <div class="label">目的地</div>
          <div class="value"  @click="selectArea(2)">
            <template v-if="endList && endList.length">
              {{endList.map(e=>e.name).join('/')}}
            </template>
            <template v-else>请选择</template>
          </div>
        </div>
      </div>

      <!--车型选择-->
      <div>
        <div class="car-select" @click="showPopup2 = true">
          选择车型
        </div>
      </div>

      <div class="btn-box">
        <van-button type="primary">查询报价</van-button>
      </div>

    </div>

    <!--地区选择-->
    <van-popup
      v-model="showPopup"
      position="bottom"
      :style="{ height: '240px' }">
      <van-area
        :columns-num="2"
        @confirm="confirmArea"
        @cancel="showPopup = false"
        :area-list="areaList"
        title=" "
      />
    </van-popup>

    <!--车型选择-->
    <van-popup
      v-model="showPopup2"
      position="bottom"
      :style="{ height: '240px' }">
      <van-area
        :columns-num="1"
        @confirm="confirmCar"
        @cancel="showPopup2 = false"
        :area-list="{province_list: carList}"
        title=" "
      />
    </van-popup>

    <!--底部-->
    <van-tabbar>
      <van-tabbar-item @click.native="tabbarItemClick(1)" icon="phone">电话咨询</van-tabbar-item>
      <van-tabbar-item @click.native="tabbarItemClick(2)" icon="wechat">微信联系</van-tabbar-item>
      <van-tabbar-item @click.native="tabbarItemClick(3)" icon="down">APP</van-tabbar-item>
    </van-tabbar>
  </div>
</template>
<script>
  import areaList from '../components/area'
  export default {
    data () {
      return {
        phone: '400-990-6596',
        areaList,
        showPopup: false,
        showPopup2: false,
        selectType: 1, // 1 出发地，2目的低，
        startList: [],
        endList: [],
        carList: {
          1: '车1',
          2: '车2',
        }
      }
    },
    watch: {
    },
    methods: {
      tabbarItemClick (val) {
        if(val === 2) { // 微信联系
          this.$router.push({
            path: '/QRcode'
          })
        } else if(val === 1){
          document.getElementById('phone').click()
        }
      },
      gridClick (path) {
        this.$router.push({
          path
        })
      },
      changeArea () {
        let a = this.startList;
        this.startList = this.endList
        this.endList = a
      },
      selectArea (val) {
        this.showPopup = true
        this.selectType = val
      },
      confirmArea (val) {
        console.log(val)
        this.showPopup = false
        if(this.selectType === 1) { // 出发
          this.startList = val
        }else{
          this.endList = val
        }
      },
      confirmCar (val) {
        console.log(val)
      }
    },
    mounted() {
    }
  };
</script>
<style lang="stylus" scoped>
  $c-border = #eee
  .area-select
    display flex
    border-bottom 1px solid $c-border
    padding-bottom 20px
    justify-content space-around
    align-items center
    .center
      font-size 30px
    .area-item
      flex 1
      .label
        color #999
      .value
        font-size 22px
        line-height 40px

    .center
      color #999

  .car-select
    font-size 22px
    line-height 50px
    border-bottom 1px solid $c-border

  .btn-box
    // color #ff644b
    padding 10px
  .my-swipe
    >>> .van-swipe-item
      height: 150px
      .img
        display block
        width 100%
  .grid-box
    >>>.van-grid-item__icon
      background-color red
      width 40px
      height 40px
      border-radius 20px
      font-size 16px
      line-height 40px
      color white
  .phone
    font-size 20px
</style>
