<template>
  <transition appear name="slide">
    <music-list :title="title" bg-image="bgImage"></music-list>
  </transition>
</template>

<script type="text/ecmascript-6">
  import MusicList from '../music-list/music-list'
  import { mapGetters } from 'vuex'
  export default {
    data () {
      return {
      }
    },
    computed: {
      title () {
        return this.toplist.topTitle
      },
      bgImage () {
        return this.toplist.picUrl
      },
      ...mapGetters([
        'toplist'
      ])
    },
    created () {
    },
    methods: {
    },
    components: {
      MusicList
    }
  }
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  .slide-enter-active, .slide-leave-active
    transition: all 0.3s

  .slide-enter, .slide-leave-to
    transform: translate3d(100%, 0, 0)
</style>
