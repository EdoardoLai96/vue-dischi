<template>
  <div id="app">
   <myHeader :discGenres="discGenres"/>
   <myMain @exportGenres='transferArray'/>
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

  },
  data(){
    return{
      discGenres : [],
    }
  },
  mounted(){
    this.transferArray()
  },
  methods:{
    transferArray(movedArray){
      this.discGenres = movedArray
    }

  },

}
</script>

<style lang="scss">
@import "./assets/style/general.scss";
</style>
