<template lang="pug">
  section#video
    video(autoplay='' muted='' id="a-satisfying-video")
      source(:src="videoUrl" type='video/mp4')
</template>

<script>
/* eslint-disable no-unused-vars */
import $ from 'jquery'
export default {
  name: 'VideoPlayer',
  data () {
    return {
      videoUrl: 'https://s3-us-west-1.amazonaws.com/db13/satisfying/g-cubes.mp4',
      audioUrl: 'https://s3-us-west-1.amazonaws.com/db13/satisfying/ff5cryst.mid'
    }
  },
  created: () => {
    setTimeout(() => {
      const vid = document.getElementById('a-satisfying-video')
      vid.onended = function (e) {
        console.log('Video has ended!')
        vid.play()
      }
    }, 10)
  }
}
</script>

<style lang="sass" scoped>
  
  @import "../_sass/utilities/_utilities.sass"

  section#video
    +h-w-t-r-b-l-pos(100vh,100vw,0,null,null,0,absolute)
    display: block
    z-index: 1
    overflow: hidden

    video
      +h-w-t-r-b-l-pos(auto,auto,50%,null,null,50%,absolute)
      position: absolute
      min-width: 100%
      min-height: 100%
      z-index: -1000
      overflow: hidden
      transform: translate(-50%, -50%)
      background-color: $white

</style>
