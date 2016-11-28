<template lang="pug">
  section#greeting
    ul.banner.greeting
      - for (var x = 0; x < 5; x++)
        li {{appname}}
</template>

<script>
/* eslint-disable no-unused-vars */
import $ from 'jquery'
import marquee from 'jquery.marquee'
export default {
  name: 'Greeting',
  data () {
    return {
      appname: 'ODDLY SATISFYING WEBSITE ODDLY SATISFYING WEBSITE ODDLY SATISFYING WEBSITE ODDLY SATISFYING WEBSITE  '
    }
  },
  created: () => {
    let initMarquee = (mclass, direction, time) => {
      $(mclass).marquee({
        direction: direction,
        duration: time,
        duplicated: true,
        startVisible: true
      })
    }
    setTimeout(() => {
      initMarquee('.greeting', 'right', 10000)
      $('.banner').animate({opacity: 1}, 100)
    }, 10)
  }
}
</script>

<style lang="sass" scoped>
  
  @import "../_sass/utilities/_utilities.sass"

  %gradient
    background: linear-gradient(270deg, #16e4af, #e4c308, #e408bf)
    background-size: 600% 600%
    -webkit-animation: gradientAnimation 29s ease infinite
    -moz-animation: gradientAnimation 29s ease infinite
    animation: gradientAnimation 29s ease infinite

  @-webkit-keyframes gradientAnimation
    0%
      background-position: 0% 50%
    50%
      background-position: 100% 50%
    100%
      background-position: 0% 50%
  
  @-moz-keyframes gradientAnimation
    0%
      background-position: 0% 50%
    50%
      background-position: 100% 50%
    100%
      background-position: 0% 50%
  
  @keyframes gradientAnimation 
    0%
      background-position: 0% 50%
    50%
      background-position: 100% 50%
    100%
      background-position: 0% 50%

  //

  ul.banner
    +h-w-t-r-b-l-pos(null,100vw,null,null,null,null,fixed)
    text-overflow: ellipsis
    white-space: nowrap
    -webkit-column-break-inside: avoid
    page-break-inside: avoid
    vertical-align: middle
    padding-left: 0
    opacity: 0
    z-index: 2

    li
      font-family: $nunito
      display: inline-block
      -webkit-column-break-inside: avoid
      page-break-inside: avoid
  
  .greeting
    @extend %gradient
    +border(top,8px,solid,$seafoam)
    +box-shadow(0,3px,12px,rgba(0, 0, 0, 0.275))
    bottom: 0
    padding: 1.5vh 0 1vh
    font-size: 8vh
    color: $yellow
    letter-spacing: 5px

</style>
