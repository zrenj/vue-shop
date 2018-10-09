<template>
  <div class="s-swiper">
    <Swipe class="s-swipe">
      <SwipeItem class="slide"><img src="https://img.alicdn.com/simba/img/TB1q0eOlaAoBKNjSZSySuuHAVXa.jpg"/></SwipeItem>
      <SwipeItem class="slide"><img src="https://aecpm.alicdn.com/tps/i2/TB10vPXKpXXXXacXXXXvKyzTVXX-520-280.jpg"/></SwipeItem>
      <SwipeItem class="slide"><img src="https://img.alicdn.com/tps/i4/TB10FkwehYaK1RjSZFnSuu80pXa.jpg_q90_.webp"/></SwipeItem>
      <SwipeItem class="slide"><img src="https://aecpm.alicdn.com/tps/i1/TB1r4h8JXXXXXXoXXXXvKyzTVXX-520-280.jpg"/></SwipeItem>

    </Swipe>
  </div>
</template>

<script>
  // 引入轮播
  import { Swipe, SwipeItem } from 'vue-swipe'
  import 'vue-swipe/dist/vue-swipe.css'
  export default {
    data () {
      return {}
    },
    components: {
      Swipe,
      SwipeItem
    },
    computed: {
      headerTitle () {
        return this.$store.getters.getHeaderTitle
      }
    },
    methods: {
      showSideBar () {
        return this.$store.dispatch('changeSideBarState', true)
        // return this.$store.commit('changeSideBarState', true)
      },
      hideSideBar () {
        return this.$store.dispatch('changeSideBarState', false)
      },
      goBack () {
        this.$router.go(-1)
      }
    }
  }
</script>

<style lang="scss" scope>
  .s-swiper{
    height: 6rem;
    width: 16rem;
  }
  .slide{
    background: green;
    img{
     height: 6rem;
     width: 16rem;
    }
  }
</style>
