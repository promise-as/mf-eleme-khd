<template>
  <div>
    <ShopHeader/>

    <div class="tab">
      <div class="tab-item">
        <router-link to="/shop/goods" replace>点餐</router-link>
      </div>
      <div class="tab-item">
        <router-link to="/shop/ratings" replace>评价</router-link>
      </div>
      <div class="tab-item">
        <router-link to="/shop/info" replace>商家</router-link>
      </div>
    </div>

    <keep-alive>
      <router-view/>
    </keep-alive>
  </div>
</template>
<script>
  import ShopHeader from '../../components/ShopHeader/ShopHeader'

  export default {
    mounted(){
      this.$store.dispatch('getInfo')
    },

    components: {
      ShopHeader
    }
  }
</script>
<style rel="stylesheet/scss" lang="scss">
  @import "../../common/sass/mixins.scss";
  .tab{
    height: 0.4rem;
    line-height: 0.4rem;
    background: #ffffff;
    @include bottom-border-1px(rgba(7, 17, 27, 0.1))
    .tab-item{
      float: left;
      width: 33.33333%;
      text-align: center;
      font-size: 0.14rem;
      color: rgb(77, 85, 93);
      a{
        display: block;
        &.router-link-active{
          color: #02a774;
        }
      }
    }
  }
</style>
