<template lang="pug">
  main#app
    Greeting
    VideoPlayer
</template>

<script>
import Greeting from './components/Greeting'
import VideoPlayer from './components/VideoPlayer'

export default {
  name: 'app',
  components: {
    Greeting,
    VideoPlayer
  }
}
</script>

<style lang="sass">
  
  @import "./_sass/utilities/_utilities.sass"
  
</style>
