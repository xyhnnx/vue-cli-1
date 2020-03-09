<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="stylus">
$c-red = #ff644b
$c-black = #101010
#app
  font-family Avenir, Helvetica, Arial, sans-serif
  -webkit-font-smoothing antialiased
  -moz-osx-font-smoothing grayscale
  text-align center
  color #2c3e50
  // 颜色覆盖
  .van-picker__cancel, .van-picker__confirm
    color $c-red
  .van-icon
    color $c-black
</style>

