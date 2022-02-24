<template>
  <div id="app">
   <myHeader @selectedGenre="transferGenre" :discGenres="discGenres"/>
   <myMain @exportGenres='transferArray' :selectedGenre="selectedGenre"/>
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
      selectedGenre : "",
    }
  },
  mounted(){
    this.transferArray(),
    this.transferGenre()
  },
  methods:{
    transferArray(movedArray){
      this.discGenres = movedArray
    },
    transferGenre(movedGenre){
      this.selectedGenre = movedGenre
    }

  },

}
</script>

<style lang="scss">
@import "./assets/style/general.scss";
</style>
