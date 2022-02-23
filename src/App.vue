<template>
  <div id="app">
   <myHeader/>
  </div>
</template>

<script>
import myHeader from './components/myHeader'

export default {
  name: 'App',
  components: {
    myHeader

  }
}
</script>

<style lang="scss">
@import "./assets/style/general.scss";
</style>
