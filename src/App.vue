<template>
  <div id="app">
   <myHeader/>
   <myMain/>
  </div>
</template>

<script>
import myHeader from './components/myHeader'
import myMain from './components/myMain'

export default {
  name: 'App',
  components: {
    myHeader,
    myMain

  }
}
</script>

<style lang="scss">
@import "./assets/style/general.scss";
</style>
